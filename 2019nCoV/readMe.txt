Mac osx 下安装python Basemap包
建议使用源代码进行手动安装，不要图省事儿用轮子装，装不上，替你试过了。

        Here是官方文档的连接

        Here是源代码资源包的连接

        到资源包里面随便找一个tar.gz下载下来，然后就可以准备安装了。装的过程中我记得需要调c++和c的一些库，建议将c++和c的编译器版本提前升级，c++编译器最好在c++11版本以上，不然调库的时候出警告还好说，出了Error就挂了。

        首先解压资源包：

tar zxvf basemap-1.0.7.tar.gz
        ok，进入basemap-1.0.7/geos-3.3.3文件夹并且修改环境变量GEOS_DIR

cd basemap-1.0.7/geos-3.3.3

export GEOS_DIR=/usr/local    #修改环境变量，待会儿用
        在当前路径下可以找到一个configure的可执行文件，执行它，并且选择配置路径为刚才设置的环境变量的路径

./configure --prefix=$GEOS_DIR
        现在开始make了

make

make install
        最后一步也就是最重要的一步来了，开始py setup.py文件！！！

python setup.py install
        执行这些步骤的时间会比较久，大概10分钟，需要耐心等待
