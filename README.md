# SmartCamera_win
������ Windows ƽ̨����������ͷ SDK��֧�� SmartLink �������������������֣�������ͷ���������á�����Ƶ�������ã��Լ� RTMP �������õȡ�

SmartCamera ּ���ṩ�����õ� SDK�����ݰ�������������ͷ���������ͷ�ȸ�������ͷ�豸��ʵ�ֶ�����ͷ��������õ����ܻ����ƶ�����

## ��ʶ SmartCamera
- SDK ����ṹ��
![Overview](overview.png)
- SmartCamera��SmartCamera ��һ������ʵ������ʹ�� SDK �������
- CameraProvider��CameraProvider ��һ���ӿڣ���Բ�ͬ���̵�����ͷ���ṩ��ͬ�� CameraProvider ʵ��
- Camera��Camera ͬ����һ���ӿڣ���Բ�ͬ�����ṩ��Ӧ��ʵ��

## ʹ�� SmartCamera
- ���� include �� lib �ļ��У������뵽���̡�
- �������룺
```c++
SmartCamera*	g = SmartCamera_getInstance();
ArrayList<CameraProvider*>*	providers = g->getSupported();
		
g->discover(providers, this, 5);

providers->destroy();


virtual void cameraDiscoverAbort(CameraProviderSource* source)
{
    ATLTRACE("ABORT: %s\r\n", source->getName());
}

virtual void cameraDiscoverTimeout(CameraProviderSource* source)
{
    ATLTRACE("TIMEOUT: %s\r\n", source->getName());
}

virtual void cameraDiscovered(CameraSource* source)
{
    ATLTRACE(TEXT("FOUND: %s\n"), source->getUrl());
    
    SmartCamera*	g = SmartCamera_getInstance();
    Camera*		camera = g->connect(source->getUrl());
    
    if(camera)
    {
        NETWORK_CONFIG*	network = camera->getNetwork();

        if(network)
            ATLTRACE(TEXT("DHCP: %s, IP: %s, MASK: %s, GATEWAY: %s, DNS1: %s, DNS2: %s\n"), network->dhcp ? "YES" : "NO", network->ip, network->mask, network->gateway, network->dns1, network->dns2);

        ....
    }
}
```


## ���������
���������κ�����ʱ������ͨ���� GitHub �� repo �ύ issues ���������⣬�뾡���ܵ�����������������⣬����д�����ϢҲһͬ������������ Labels ��ָ������Ϊ bug ����������
[ͨ������鿴���е� issues ���ύ Bug](https://github.com/azhisoft/SmartCamera_win/issues)
