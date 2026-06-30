# 不建议在QQ群使用本插件


## jmcomic_HoshinoBot

下载并加密指定jmid的漫画并上传到群文件。基于[hect0x7/JMComic-Crawler-Python](https://github.com/hect0x7/JMComic-Crawler-Python)，适用于[HoshinoBot](https://github.com/Ice9Coffee/HoshinoBot)。  
需要Python3.9+

## 安装方法
1. 在module目录下克隆本仓库 `git clone https://github.com/NekoYSure/jmcomic_Hoshino.git`
2. 下载依赖 `pip install -U "jmcomic>=2.7.0" PyPDF2 img2pdf pyzipper pyyaml`  
3. 复制`jm_config_example.yml`到`jm_config.yml`
4. 在`__bot__.py`的`module`中添加`jmcomic_HoshinoBot`
5. 在群内发送`enable jmcomic`以启用本插件

## 遗留问题
- 下载的文件会全部积攒在硬盘中，没有做自动清理。  

## 更新日志
2025.05.06 可用  
2025.05.08 加密PDF文件的输出路径读取`jmcomic_config.yml`by[@NekoYSure](https://github.com/NekoYSure)；本地存在目标jmid文件时直接上传。增加依赖`pyyaml`。  
2025.05.09 可选上传1.未加密pdf、2.加密pdf、3.加密zip+未加密pdf、4.加密zip+加密pdf。增加依赖`pyzipper`。  
2025.05.10 增加了一个记录正在下载的列表，尝试下载已经在下载中的本子时发提示并return。优化提示。  
2026.06.30 同步`JMComic-Crawler-Python 2.7.0`的移动端API域名配置，移除过期的`www.jmapiproxyxxx.vip`示例域名，并启用API域名自动更新。  



## 碎碎念
随便写写，可能不会长期维护。  
**搞这个的bot，不会长久的。**  
也可以看看[Fatfish588/jmid2name-hoshino](https://github.com/Fatfish588/jmid2name-hoshino)，这个是jmid转漫画名字的。  

`jm_config.yml`里的`dir_rule.base_dir`是下载的全部图片文件路径，`plugins.after_album`里`img2pdf.kwargs.pdf_dir`是输出PDF路径，如果是windows用的话要改成windows的路径格式。这个配置文件的其他设置可以参考[jmcomic配置文件指南](https://jmcomic.readthedocs.io/zh-cn/latest/option_file_syntax/#)。  
如果你已经从旧版本复制过`jm_config.yml`，请删除`client.domain.api`里的`www.jmapiproxyxxx.vip`，或者直接用新的`jm_config_example.yml`重新复制；新版会自动获取可用API域名。  
加密PDF、压缩包也都会输出到35行的这个路径  

搞加密zip主要是防止内鬼用手机QQ内置阅读器打开PDF。  
  
默认情况下，仅允许SUPERUSER权限的用户开启本插件，可以按需求该manage_priv。  
  
默认情况下，文件密码是jmid的倒序，可以改`enctypt_pdf`和`encrypt_zip`的password传参设置别的密码。  
  
~~`llob_cross_host_download_file`这个我只试了LLOneBot。根据[NapCat文档](https://napneko.github.io/onebot/napcat#napcat-%E8%B5%84%E6%BA%90-url-%E5%8F%82%E6%95%B0%E7%B1%BB%E5%9E%8B)，这么写对于NapCat似乎不太适用。有人用的话试一下吧(x)~~  
↑群友说不用改
    
<br>

![](https://s2.loli.net/2025/05/07/3tic9aP45MJAqGw.png)
