### DOL��װ�ʼ�
1. ��װ��Ҫ�Ļ���
    - $ sudo apt-get update
    - $ sudo apt-get install ant
    - $ sudo apt-get install openjdk-7-jdk
    - $ sudo apt-get install unzip
2. �����ļ����߽��ļ������������������
3. ��ѹ�ļ�
    - �½�dol���ļ���($ mkdir dol)
    - ��dolethz.zip��ѹ�� dol�ļ�����($ unzip dol_ethz.zip -d dol)
    - ��ѹsystemc($ tar -zxvf systemc-2.3.1.tgz)
4. ����systemc
    - ��ѹ�����systemc-2.3.1��Ŀ¼��($	cd systemc-2.3.1)
    - �½�һ����ʱ�ļ���objdir($ mkdir objdir)
    - ������ļ���objdir($ cd objdir)
    - ����configure($ ../configure CXX=g++ --disable-async-updates)
     
       ���н������

        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/1.jpg)
    - ����($ sudo make install)          �������Ŀ¼�ļ�����($ cd ..$ ls)
    
       ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/2.jpg)
    - ��¼��ǰ�Ĺ���·��($ pwd)
5. ����dol
    - ����ո�dol���ļ���($ cd ../dol)
    - �޸�build_zip.xml�ļ����ҵ�������λ�
    <property name="systemc.inc" value="YYY/include"/>
    <property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>
    ��YYY�ĳ���ҳpwd�Ľ����ע�⣬����  64λ ϵͳ�Ļ�����lib-linuxҪ�ĳ�lib-linux64��
    - ����($ ant -f build_zip.xml all)
    ���ɹ�����ʾbuild successful����ͼ

        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/3.jpg)
    - �����������е�һ�����ӣ�����build/bin/mian·����($	cd build/bin/main)��
    Ȼ�����е�һ������($ ant -f runexample.xml -Dnumber=1),�����ͼ
    
        ![image](https://github.com/mmbbmm/ES2016_14353297/blob/master/picture/4.jpg)

### DOL�������

    �ֲ�ʽ�����㣨DOL����һ����ܣ�ʹӦ�ó���ģ��룩�Զ�ӳ�䵽�ദ����SHAPES�ܹ�ƽ̨���͹�������������������ɣ�
    DOLӦ�ó����̽ӿڣ� �͹���������һ������ͨ�ų���ʹ����״�ֲ�ƽ̨������Ӧ�ó���ı�̡�ʹ����Щ����Ӧ�ó���Ա���Ա�д���򣬶������˽�ײ�ܹ�����ϸ֪ʶ����ʵ�ϣ���Щ����������Ӳ����ص������HDS�����һ�����ơ�
    DOL���ܷ��棺 �ṩ����Ա�����Բ�����Ӧ�ó��򣬹��ܷ������Ѿ��γɡ�����Ӧ�ù�����֤����������������Ӧ�ó��򼶻�õ����ܲ�����
    DOLӳ���Ż��� ��DOLӳ���Ż���Ŀ���Ǽ���һ��Ӧ�ó�������ӳ�䵽��״�ܹ�ƽ̨���ڵ�һ�����У�����XML�淶��ʽ�Ѷ�������������һ�����󼶱��Ӧ�ó������ϵ�ṹ��������ˣ����б�Ҫ�ģ��Ի��׼ȷ�����ܹ��ư�����Ϣ��
    
### ʵ�����&ʵ���ĵ�
1.ʵ��1&ʵ��2

    ������ʵ����Ҫ�����û����Լ�������Ϥgithub��markdown�﷨��ͨ��������ʵ���Ҷ�dol�Ŀ���Լ��ֿ��Markdown���÷����˳������˽⣬Ϊ֮��Ľ�һ��ѧϰ�����˻�����