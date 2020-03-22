# Maker
101camp course for Enjoy Maker ;-)


## bg.
多年积累, 终于有了一门 软硬通吃 课程;


蟒营创客课程官网发布

## goal

快速发布课程官网

- 使用 github-pages 服务
- 需要两个仓库的本地配合
    + 101camp/mk        ~ 内容撰写
    + 101camp/mk.101.camp   ~ 自动发布


## process
> 维护过程

本地先分别将两个仓库并排 clone 到本地:

    path/2/合适目录:
        +- mk        ~ 内容撰写
        |   +- site/    <- 链接到隔壁 ln -s ../dj.101.camp
        +- mk.101.camp   ~ 自动发布

效果, 在 mk 中:

    ༄  ls -hl
    total 28K
        CNAME
        LICENSE
        README.md
        _theme
        _trigger
        docs
        img
        mkdocs.yml
        site -> ../mk.101.camp/
        tasks.py

> 安装 invoke

检验: 

    ༄  pip show invoke
    Name: invoke
    Version: 1.2.0
    Summary: Pythonic task execution
    Home-page: http://docs.pyinvoke.org
    Author: Jeff Forcier
    Author-email: jeff@bitprophet.org
    License: BSD
    Location: /Users/zoomq/.pyenv/versions/3.6.3/envs/DU363/lib/python3.6/site-packages
    Requires:
    Required-by:


以及相关模块, 可以用 `pip install -r requirements.txt` 批量安装

> 200322 增补

- 追加了依赖的 `mkdocs-bootswatch` 

### 发布
> 对应 mk/docs 中修改文章后


    ༄  inv pub
    auto deplo NOW:
    /opt/data/Sites/101.camp/_running/mk
    INFO    -  Cleaning site directory
    INFO    -  Building documentation to directory: /opt/data/Sites/101.camp/_running/mk/site
    /opt/data/Sites/101.camp/_running/mk
    On branch master
    Your branch is up-to-date with 'origin/master'.

    Changes not staged for commit:
    ...

    To github.com:101camp/mk.101.camp.git
       2ef6c56..edbca34  master -> master

         powded by pub101CAMP v.190721.2342

> 即自动完成一系列编译/整理/同步/发布/... 的行为

>> PS:

- 参考: [.gitconfig](https://gitlab.com/pythonicamp/course/101camp0mk/-/blob/master/.gitlab/.gitconfig)
- 使用了自定指令, 以免节省操作



[蟒营™ Maker 入门班](http://mk.101.camp/) 即可看到更新

包含其它功能有:

    ༄  inv -l
    Available tasks:

      bu    usgae MkDocs build AIM site
      pub   <- auto deploy new site version base multi-repo.
      ver   echo crt. verions

## logging:

- 200319 Samuche init.
    + ZQ cp as mk.101.camp
- 190721 ZQ init.
