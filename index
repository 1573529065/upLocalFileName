<?php
header("Content-type: text/html; charset=utf-8");

//利用PHP目录和文件函数遍历用户给出目录的所有的文件和文件夹，修改文件名称
function fRename($dirname)
{
    if (!is_dir($dirname)) {
        echo "{$dirname}不是一个有效的目录！";
        exit();
    }
//    $handle = opendir($dirname);

    $arr = scandir($dirname);
    foreach ($arr as $key => $item) {
        if ($item != '.' && $item != '..') {
            echo "<br>将名为：" . $item . "\n\r";
            $curDir = $dirname . $item;

            if (is_dir($curDir)) {
                fRename($curDir);
            } else {
                $path = pathinfo($curDir);
                $newname = $path['dirname'] . '\a0821_' . $path['filename'] . '.' . $path['extension'];

                echo '修改为:' . $newname . "\r\n";

                rename($curDir, $newname);
            }
        }
    }
}

//给出一个目录名称可以是相对路径，也可以是绝对路径
//fRename("D:\phpStudy\PHPTutorial\WWW\商品\\");
$path = __DIR__ . '\123\\';
fRename($path);

exit();
?>
