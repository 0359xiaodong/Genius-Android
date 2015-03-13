## Version 1.0.0 Guide

[`����`](CapriceGuide_Kit_1.0.0_ZHH) [`English`](CapriceGuide_Kit_1.0.0) [`Guides`](GuideCatalog) 

## ����ģ��

* `command`
  > *  �����������ִ�������й���
  > *  ��`ProcessBuilder`��������
  > *  �����������д��󣬽�����й���
  > *  һ������������ȡ�����������ɿ���
  > *  ��ͬ�����첽��ʽִ�У��ɻص��¼�

* `net `
  > *  һ��`Ping` `DNS` `TelNet` `TraceRoute`
  > *  �ɿ��ƣ���ȡ�������ع���ϸ������
  > *  ������·�����񣬿���40s���Ҳ������

* `util`
  > *  `HashKit`  �ַ������ļ�`MD5`��ȡ
  > *  `Tools` `ID` `SN` ȷ���豸Ψһ��ʶ
  > *  `Log` ��ϵͳLogһ��ʹ�ü򵥣�һ������
  > *  `Log` �ɴ洢��־���ļ�������������
  > *  `Log` ������¼����������������ʾ��־��Ϣ
  > *  `FixedList` �������У��Զ����������ֶ�������
  > *  `UiKit` ֧�����߳�ͬ�����첽�л������̲߳���
 > *  `GeniusException` �Զ����쳣�࣬�ɽػ��쳣�����Զ��崦��



## ��ȡ��

* `Star` �� `Fork` ��Ŀ��
* `MavenCentral` Զ�̵��� :

```gradle
// ����Ŀ "build.gradle" �����
dependencies {
  compile 'com.github.qiujuer:genius-kit:3.0.0-SNAPSHOT'
}

```
## ������־

* �汾��`1.0.0`
* ���ڣ�`2015-03-07`
* ��־��[`������־`](CapriceNotes_Kit_1.X)

## ʹ�÷���

##### ��ʼ��������

```java
GeniusKit.initialize(Application application);
GeniusKit.dispose();

```
##### `command` ģ��


```java
// ִ�������̨�����Զ�����
// ���÷�ʽ��ProcessBuilder���η�ʽһ��
// timeout������ʱֵ,��ѡ����
// params��ִ�в������磺"/system/bin/ping","-c", "4", "-s", "100","www.baidu.com"
Command command = new Command(int timeout, String... params);

// ͬ����ʽ
// ��ɺ���ֱ�ӷ���
String result = Command.command(new Command(Command.TIMEOUT, "..."));

// �첽��ʽ
// ������¼��ص���ʽ����
Command command = new Command("...");
Command.command(command, new Command.CommandListener() {
    @Override
    public void onCompleted(String str) {
    }
    @Override
    public void onCancel() {
    }
    @Override
    public void onError(Exception e) {
    }
});

// ȡ��һ����������
Command.cancel(Command command);

// ���� Command ����
Command.restart();

// ����
// ���� ��Genius.dispose()�� ����ʱĬ�ϵ���
Command.dispose();

```

##### `net` ģ��

```java
// Ping
// ������������IP
// ������Ƿ�ִ�гɹ�����ʱ������
Ping ping = new Ping("www.baidu.com");
// ��ʼ
ping.start();
// ����
if (ping.getError() == NetModel.SUCCEED) {}
else {}
...
����������Ping����
...

```

##### `util` ģ��

```java
// ===================FixedList===================
// �̶����ȶ���
// ��ָ�����ȣ�ʹ�÷�������ͨ��������
// ������Ԫ�������ﵽָ������ʱ������Ԫ��
// ͷ������β��������β������ͷ������

// ��ʼ����󳤶�Ϊ5
FixedList<Integer> list = new FixedList<Integer>(5);

// ��ȡ�������
list.getMaxSize();
// ������󳤶ȣ���С����ʱ���Զ�ɾ��ͷ������Ԫ��
list.setMaxSize(3);

// ��ʹ��List����
List<Integer> list = new FixedList<Integer>(2);


// ====================HashKit==================
// ��ϣ���㣨Md5��
// �ɼ����ַ������ļ�Md5ֵ

// ��ȡ�ַ���MD5
String hash = HashKit.getMD5String(String str);
// ��ȡ�ļ�MD5
String hash = HashKit.getMD5String(File file);


// ======================Log======================
// ��־��
// ���÷�����ʹ��Android Log����һ��
// ���������Ƿ�洢��־��Ϣ
// �ɿ�����־��Ϣ��SD��
// ��������������¼��ص�������ʵʱ��ʾ��־

// ��ӻص�
// �ص���
Log.LogCallbackListener listener = new LogCallbackListener() {
    @Override
    public void onLogArrived(Log data) {
        ...
    }
};
// ���
Log.addCallbackListener(listener);

// �Ƿ����ϵͳAndroid Log���ɿ����Ƿ���ʾ
Log.setCallLog(true);
// �Ƿ���д���ļ����ļ������������ļ���С��Mb��
// Ĭ�ϴ洢�ڳ���Ŀ¼/Genius/Logs
Log.setSaveLog(true, 10, 1);
// �����Ƿ�����ⲿ�洢�������
// �����������ⲿ�豸��SD��ʱ����������־�ļ����ⲿ�洢
// �˲����������Ƿ���д���ļ����ܣ�δ������˷�����Ч
Log.setCopyExternalStorage(true, "Test/Logs");

// �����ڲ��洢����־�ļ����ⲿ�洢��SD��
// �˲����������Ƿ���д���ļ����ܣ�δ������˷�����Ч
Log.copyToExternalStorage("Test/Logs");

// ������־�ȼ�
// ALL(ȫ����ʾ)��VERBOSE��ERROR���εݼ�
Log.setLevel(Log.ALL);

// �����־
Log.d(TAG, "DEBUG ");


// ====================Tools====================
// ���ù��߰�
// ȫ��Ϊ��̬�������Ժ������������

// ����
Tools.sleepIgnoreInterrupt(long time);
// �����ļ�
Tools.copyFile(File source, File target);
// AndroidId
Tools.getAndroidId(Context context);
// SN���
Tools.getSerialNumber();

```
