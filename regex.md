## 保留两位小数，如果第三位不为0，也需要保留   $price=~s/(.\d\d[1-9]?)\d*/$1/g

## 回复邮件p58 while($line= < > ){
    if($line =~ m/^\s*$/){
        last; #立即结束循环
    }
    if($line =~ m/^subject:(.*)/i){
        $subject=$1;
    }
    if($line =~m/^Date:(.*)/i){
        $date=$1;
    }
    if($line =~ m/^Replay-to: (.*)/i){
        $replay_address=$1;
    }
    if($line =~ m/^From: (/S/) \(([^()*])\){
        $replay_address=$1;
        $replay_name=$2;
    }
}