### 如何使用PyQt for Mac

~~~~
1.首先需要安装 anaconda3 。 
  这样就会有PyQt的UI工具：/opt/anaconda3/bin/Designer.app

2.安装 PyQt 
  pip install 
  PyQt5-5.10-5.10.0-cp35.cp36.cp37-abi3-macosx_10_6_intel.whl

3.配置PyCharm 工具
  1) 打开Designer.app 的配置
        Tools > External Tools > 
            Name: Qt Desiger
            Program: /opt/anaconda3/bin/Designer.app
            Working directory: (默认生成) /opt/anaconda3/bin

  2) 将Designer.app 生成的ui文件 转成py文件
        a.可以使用命令行 将ui生成py：pyuic5 -o xx.py xx.ui
        b.在PyCharm中配置：
          Tools > External Tools > 
            Name: Qt UIC
            Program: /opt/anaconda3/envs/Application/bin/python （指向python）
            Parameters: -m PyQt5.uic.pyuic  $FileName$ -o $FileNameWithoutExtension$.py (双击ui文件选中后，使用Tools)
            Working directory: $FileDir$