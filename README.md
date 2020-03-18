# django
101camp course for Enjoy Django ;-)

## bg.

班长多年积累, 终于有了一门纯 IT 技术课程;

## goal

快速发布课程官网

- 使用 github-pages 服务
- 需要两个仓库的本地配合
    + 101camp/django        ~ 内容撰写
    + 101camp/dj.101.camp   ~ 自动发布


## process
> 维护过程

本地先分别将两个仓库并排 clone 到本地:

    path/2/合适目录:
        +- django        ~ 内容撰写
        |   +- site/    <- 链接到隔壁 ln -s ../dj.101.camp
        +- dj.101.camp   ~ 自动发布

效果, 在 django 中:

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
        site -> ../dj.101.camp/
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


### 发布
> 对应 django/docs 中修改文章后


    ༄  inv pub
    auto deplo NOW:
    /opt/data/Sites/101.camp/_running/django
    INFO    -  Cleaning site directory
    INFO    -  Building documentation to directory: /opt/data/Sites/101.camp/_running/django/site
    /opt/data/Sites/101.camp/_running/django
    On branch master
    Your branch is up-to-date with 'origin/master'.

    Changes not staged for commit:
    ...

    To github.com:101camp/dj.101.camp.git
       2ef6c56..edbca34  master -> master

         powded by pub101CAMP v.190721.2342

> 即自动完成一系列编译/整理/同步/发布/... 的行为


[蟒营 Djnago 入门班](http://dj.101.camp/) 即可看到更新

包含其它功能有:

    ༄  inv -l
    Available tasks:

      bu    usgae MkDocs build AIM site
      pub   <- auto deploy new site version base multi-repo.
      ver   echo crt. verions

## logging:

- 190721 ZQ init.
