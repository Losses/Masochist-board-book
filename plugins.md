# 插件的安装和使用

我们在 Masochist-board 中置入了一个简易的插件系统，您可以简单的从插件市场中下载插件，并上传到服务器上。

## 插件的安装配置与安装

从插件市场下载回来的文件为一个压缩包，每个插件都有一个配置文件 config.php 您可能需要编辑此文件，进行简单的配置操作。

我们在这里以匿名用户管理插件SweetCookies为例。

这是该插件的config.php
    
    $plugin_info = [
        "IDENTIFICATION" => "losses.sweet.cookie"
        //这是插件的唯一ID，用于多个插件之间互相协作，您不应改动此内容
    ];
    
    $plugin_injector = [
        "HOOK-BEFORE_NEW" => "HOOK-BEFORE_NEW.php"
        //规定了插件的运行方式，您不应改动此内容
    ];
    
    $plugin_config = [
        "EX_ENABLE_COOKIE" => true,
        //此选项指定了是否开放匿名账号获取，true为开放，false为不开放。
        "EX_EXPIRATION_TIME" => 30,
        //此选项规定了多长时间内不访问网站就会注销该账号，以日为单位。
        "EX_HASH_IP" => true
        //此选项规定了是否为IP进行加密以保护访客隐私。
    ];

如果插件包不包含 config.php 则表示该插件无需特别配置，您可忽略上面的内容。

接下来，将插件文件夹上传到 plugins 目录下，每个插件一个目录。系统会自动扫描目录中的文件改动，并自动启用新插件。

