�����setup���ػ���֮��ִ�У�vagrant.exe ssh
��������ͼƬ��˵�����ػ�����һ��С���⣺

�������googleһ�»ᷢ��Hyperledger�ٷ���˵����https://github.com/hyperledger-archives/fabric/wiki/Troubleshooting-devenv-provisioning
���ǲ�û�и������������
�����ʾ��Ӱ�죺�޷�ִ��make docker ����makeһЩ�������ʱ���ʧ�ܡ�


setup_dev�����п�����һЩ���⣺

��ִ�е�6����vagrant.exe up�����п��������Ĵ�����ʾ��
1.��ʾubuntu/xenial64 ����timeout
2.��װdocker-ce������repository��ַ����ʧ�ܻ�timeout
3.zookeeper�汾3.4.9��kafka�汾0.9.0.1�Ѿ���������

��ν����
1.ʹ��Ѹ��ֱ������һ�����õ�ubuntu�������������ѡ��https://vagrantcloud.com/hyperledger/boxes/fabric-baseimage/versions/0.3.0/providers/virtualbox.box
  �������ļ�������Ϊvirtualbox.box��Ȼ��ִ�У�vagrant.exe box add virtualbox.box  --name fabric
  �޸�Vagrantfile:
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
	��
Vagrant.configure("2") do |config|
  config.vm.box = "fabric"
2.�޸�setup.sh�����Ӱ�����repository��add-apt-repository "deb [arch=amd64] http://mirrors.aliyun.com/docker-ce/linux/ubuntu
$(lsb_release -cs) stable"
3.�޸�setup.sh������zookeeper��kafka�İ汾�����ڵ��°汾

���⽨��GO�İ汾������1.9.2��Node�İ汾������8.9.0
