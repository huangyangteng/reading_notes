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
## 大的数值之间加入逗号 12345678 -》 12,345,678 左边有数字右边数字刚好是三的倍数
$prop =~ s/(?<=\d)(?=(:\d\d\d)+$)/,/g
缺点 不能匹配 ...tone of 12345hz
#\b 表示的是一边匹配单词，一边不匹配单词 一侧是\w一侧不是\w   \b\w{3}\b  左边的\b就是(?<!\w)(?=\w)   右边的\w就是  (?<=\w)(?!\w)  
\b就等价于   (?<!\w)(?=\w) | (?<=\w)(?!\w)
$text =~ s/(?<=\d)(?=(:\d\d\d)+(?!\d))/,/g