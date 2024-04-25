 可以自选内容，支持多种，可以用来小赚                                     对接方法
对接地址
本站地址
标识
//本站标识 放在/Checkorder/xdjk.php 文件
"aw" => "暗网",
29查课对接代码
//本站学习平台查课接口 放在/Checkorder/ckjk.php 文件
    if ($type == "aw") {
        $data = array("uid" => $a["user"], "key" => $a["pass"], "school" => $school, "user" => $user, "pass" => $pass, "platform" => $noun, "kcid" => $kcid);
        $ace_rl = $a["url"];
        $ace_url = "$ace_rl/api.php?act=get";
        $result = get_url($ace_url, $data);
        $result = json_decode($result, true);
        return $result;
    }
    
//本站学习平台进度接口放在checkorder/jdjk.php内
else if ($type == "aw") {
        $uu_rl = $a["url"]; 
        $uu_url = "$uu_rl/api/search?uid=".$a["user"]."&key=".$a["pass"]."&kcname=".$kcname."&username=".$user."&cid=".$d["noun"]; $result = get_url($uu_url,$data); $result = json_decode($result, true); if ($result["code"] == "1") { foreach ($result["data"] as $res) { $yid = $res["id"]; $kcname = $res["kcname"]; $status = $res["status"]; $process = $res["process"]; $remarks = $res["remarks"]; $kcks = $res["courseStartTime"]; $kcjs = $res["courseEndTime"]; $ksks = $res["examStartTime"]; $ksjs = $res["examEndTime"]; $b[] = array("code" => 1, "msg" => "查询成功", "yid" => $yid, "kcname" => $kcname, "user" => $user, "pass" => $pass, "ksks" => $ksks, "ksjs" => $ksjs, "status_text" => $status, "process" => $process, "remarks" => $remarks); } } else { $b[] = array("code" => -1, "msg" => $result["msg"]); } return $b; }
        
//本站学习平台下单接口放在checkorder/xdjk.php内
        if ($type == "aw") {
        $data = array("uid" => $a["user"], "key" => $a["pass"], "platform" => $noun, "school" => $school, "user" => $user, "pass" => $pass, "kcname" => $kcname, "kcid" => $kcid, "shichang" => $shichang, "score" => $score);
        $ace_rl = $a["url"];
        $ace_url = "$ace_rl/api.php?act=add";
        $result = get_url($ace_url, $data);
        $result = json_decode($result, true);
        if ($result["code"] == "0") {
        $b = array("code" => 1, "msg" => "下单成功");
        } else {
        $b = array("code" => -1, "msg" => $result["msg"]);
        }
    return $b;
    }
    
//本站学习平台补刷接口放在checkorder/bsjk.php内
    if ($type == "aw") {
        $data = array("uid" => $a["user"], "key" => $a["pass"], "id" => $yid);
        $ace_rl = $a["url"];
        $ace_url = "$ace_rl/api.php?act=budan";
        $result = get_url($ace_url, $data);
        $result = json_decode($result, true);
        return $result;
    }# -
可以自选内容，支持多种，可以用来小赚






加q了解：3156055582
