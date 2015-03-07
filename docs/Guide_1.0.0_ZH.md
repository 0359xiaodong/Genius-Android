## Version 1.0.0 Guide

[`����`](Guide_1.0.0_ZH) [`English`](Guide_1.0.0) [`Guides`](GuideCatalog) 


## Genius-Android��ʲô?

**Genius-Android** �� **Android** ��һЩ���õĵķ�������, **Genius** �ṩ5��������飺

`app`��**Ui**�� `material`��**�ؼ�**�� `command`��**������**�� `net tool`��**Ping��Dns...**�� `util`��**���÷���,��**��


## ��ͼ

##### MaterialButton
![MaterialButton](https://raw.githubusercontent.com/qiujuer/Genius-Android/resource/images/first/6A589E80.gif)

##### Themes
![Themes](https://raw.githubusercontent.com/qiujuer/Genius-Android/resource/images/first/82891FA0.png)

##### BlurKit
![BlurKit](https://raw.githubusercontent.com/qiujuer/Genius-Android/resource/images/first/EA925260.png)


## ����ģ��

* `app`
  > *  `ToolKit` ֧�����߳�`ͬ��`��`�첽`�л������̲߳���
  > *  `BlurKit` ֧��`Java`��`Jni`ʹ��`StackBlur`�㷨ģ��ͼƬ

* `material`
  > *  ���� `opensans` `roboto`
  > *  ��ɫ `none` `dark` `light`
  > *  �ؼ� `MaterialButton`

* `command`
  > *  �����������ִ�������й���
  > *  ��`ProcessBuilder`��������
  > *  �����������д��󣬽�����й���
  > *  һ������������ȡ�����������ɿ���
  > *  ��ͬ�����첽��ʽִ�У��ɻص��¼�

* `net tool`
  > *  һ��`Ping` `DNS` `TelNet` `TraceRoute`
  > *  �ɿ��ƣ���ȡ�������ع���ϸ������
  > *  ������·�����񣬿���40s���Ҳ������

* `util`
  > *  `AppContext` ȫ�֡���ȡ������
  > *  `HashUtils`  �ַ������ļ�`MD5`��ȡ
  > *  `ID` `SN` ȷ���豸Ψһ��ʶ
  > *  `Log` ��ϵͳLogһ��ʹ�ü򵥣�һ������
  > *  `Log` �ɴ洢��־���ļ�������������
  > *  `Log` ������¼����������������ʾ��־��Ϣ
  > *  `FixedList` �������У��Զ����������ֶ�������


## ��ȡ��

* `Star` �� `Fork` ��Ŀ��
* `release` �ļ����е� `*.jar` ���� `*.aar` �ļ���ֱ�ӵ�����Ŀ�С�
  *  `*.jar` �޷�ʹ�ÿؼ���Դ��������� `R..`��
  *  `*.aar` ��ʹ�����е���Ϳؼ��Լ�����ȡ�
  *  `*.aar` �������뷽����
* `Eclipse` [`Eclipse�������`](EclipseImport)
* `Android Studio` :
  *  `*.aar` ���ص��뷽����
  
  ```gradle
  // �追�� "genius_1.0.0.aar" �� "libs" Ŀ¼
  android {
      repositories {
          flatDir { dirs 'libs' }
      }
  }
  dependencies {
      compile (name:'genius_1.0.0', ext:'aar')
  }

  ```

  *  `*.aar` `MavenCentral`Զ�̵��룺
  
  ```gradle
  // ����Ŀ "build.gradle" �����
  // ���追���κ��ļ����ȴ�����������ɼ���ʹ��
  dependencies {
      compile 'com.github.qiujuer:genius:1.0.0'
  }

  ```


## ������־

* �汾��`1.0.0`
* ���ڣ�`2014-12-26 00:20`
* ��־��[`������־`](NotesFirst)


## ʹ�÷���

##### ��ʼ��������

```java
Genius.initialize(Application application);
Genius.dispose();

```


##### `app` ģ��

```java
// "Runnable" ʵ������ "run()" ����
// "run()" ���������߳��У��������н��н������
// ͬ���������߳�,�ȴ����̴߳�����ɺ����ִ�����߳�
ToolKit.runOnMainThreadSync(Runnable runnable);
// �첽�������߳�,����ȴ�
ToolKit.runOnMainThreadAsync(Runnable runnable);
// ͬ���������߳�ֻ�ȴ�ָ��ʱ��
// @param runnable Runnable �ӿ�
// @param waitTime ���̵߳ȴ�ʱ��
// @param cancel   �ȴ�ʱ�䵽ʱ�Ƿ�ȡ�����߳�ִ�и�����
ToolKit.runOnMainThreadSync(Runnable runnable, int waitTime, boolean cancel)

// "bitmap" �������ͼƬ
// "radius" ͼƬģ���뾶
// "canReuseInBitmap" �Ƿ�ֱ��ʹ�� "bitmap" �н���ģ��,
// "false" ����½����� "bitmap" �ĸ�������ģ��
// ��"Java"��ʵ��ͼƬģ��
BlurKit.blur(Bitmap bitmap, int radius, boolean canReuseInBitmap);
// ��"Jni"��ʵ��ͼƬģ��,����"Jni"����ͼƬ��"Bitmap"
BlurKit.blurNatively(Bitmap bitmap, int radius, boolean canReuseInBitmap);
// ��"Jni"��ʵ��ͼƬģ��,����"Jni"����ͼƬ "���ؼ���"
BlurKit.blurNativelyPixels(Bitmap bitmap, int radius, boolean canReuseInBitmap);

```


##### `material` ģ��

```xml
// �����ڸ�������ָ����
<LinearLayout
    ...
    xmlns:material="http://schemas.android.com/apk/res-auto"/>

// ������ʽ������ͼTheme
// �ṩ���壺`opensans` `roboto`
// �����ϸ��`bold` `extrabold` `extralight` `light` `regular`

// ==================MaterialButton==================
<net.qiujuer.genius.material.MaterialButton
    ...
    material:gm_textAppearance="light"
    material:gm_fontFamily="opensans"
    material:gm_fontWeight="bold"
    material:gm_isMaterial="true"
    material:gm_isAutoMove="true"
    material:gm_theme="@array/grass" />

// `gm_textAppearance`: ָ��������ɫ��Ĭ��Ϊ `none`
// `gm_fontFamily`: ָ�����������е�һ������
// `gm_fontWeight`: ָ�������ϸ
// `gm_isMaterial`: �Ƿ�� Material ������Ĭ�� `true`
// `gm_isAutoMove`: �����Ƿ��Զ��ƶ������ģ�Ĭ�� `true`
// �����󶯻�������ԭ����ɢ������� `XY` ���꽫�����Ŀ�£
// `gm_theme`: ָ��������ʽ��12������ѡ

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


##### `net tool` ģ��

```java
// Ping
// ������������IP
// ������Ƿ�ִ�гɹ�����ʱ������
Ping ping = new Ping("www.baidu.com");
// ��ʼ
ping.start();
// ����
if (ping.getError() == NetModel.SUCCEED) {
    ...
} else {
    ...
}
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
// ʹ��Queue�������Ԫ��
list.offer(0);
// ʹ��List�������Ԫ��
list.add(1);
// ĩβ����Ԫ����addһ��
list.addLast(1);
// ��ͷ�����룬ɾ��β������Ԫ��
list.addFirst(19);
// ���һ���б�
list.addAll(new ArrayList<Integer>());

// ��ȡ�������
list.getMaxSize();
// ������󳤶ȣ���С����ʱ���Զ�ɾ��ͷ������Ԫ��
list.setMaxSize(3);

// ����poll��ʽ����Ԫ��
int i = list.poll();
// remove �� poll ���ƣ�����������ɾ��Ԫ�أ���ɾ��һ��Ԫ��
list.remove();
// ��ղ���
list.clear();

// ��ʹ��List����
List<Integer> list = new FixedList<Integer>(2);


// ====================HashUtils==================
// ��ϣ���㣨Md5��
// �ɼ����ַ������ļ�Md5ֵ

// ��ȡ�ַ���MD5
String hash = HashUtils.getStringMd5(String str);
// ��ȡ�ļ�MD5
String hash = HashUtils.getFileMd5(File file);


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
Log.setLevel(Log.INFO);

// �����־
Log.v(TAG, "��־ VERBOSE ");
Log.d(TAG, "��־ DEBUG ");
Log.i(TAG, "��־ INFO ");
Log.w(TAG, "��־ WARN ");
Log.e(TAG, "��־ ERROR ");


// ====================ToolUtils====================
// ���ù��߰�
// ȫ��Ϊ��̬�������Ժ������������

// ����
ToolUtils.sleepIgnoreInterrupt(long time);
// �����ļ�
ToolUtils.copyFile(File source, File target);
// AndroidId
ToolUtils.getAndroidId(Context context);
// SN���
ToolUtils.getSerialNumber();

```


## ����Ȩ��

```xml
    <!-- ���� Ȩ�� -->
    <uses-permission android:name="android.permission.INTERNET" />
    <!-- ��־д�ļ� Ȩ�� -->
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
    <!-- getDeviceId Ȩ�� -->
    <uses-permission android:name="android.permission.READ_PHONE_STATE"/>
    
```


## ���ǿ�����

���ر���Ŀ,��Ŀ�ɵ��뵽 `Android Studio`��Android Studio >= 1.0

��Ŀ�к���һ�����Լ�һ��������Ŀ���ɽ��⵼�뵽�Լ�����Ŀ��ʹ�á�

`Eclipse` ���޷�ֱ�ӵ�����Ŀ�����Ƚ���һ����Ŀ���ն�ӦĿ¼��������Ŀ�С�


## ����

��ʹ�������κ����⣬��ӭ�ܼ�ʱ�������ң�������������ϵ��ʽ���ҽ���

* ��Ŀ��[`�ύBug���뷨`](https://github.com/qiujuer/Genius-Android/issues)
* �ʼ���[`qiujuer@live.cn`](mailto:qiujuer@live.cn)
* QQ�� `756069544`
* Weibo�� [`@qiujuer`](http://weibo.com/qiujuer)
* ��վ��[`www.qiujuer.net`](http://www.qiujuer.net)


## ����������

����Ȥ��дһ��`���`�Ķ���������ϲ��Ҳ���к�ˮ��ϣ����ϲ���ҵ���Ʒ��ͬʱҲ��֧��һ�¡�
��Ȼ����Ǯ����Ǯ����֧����: `qiujuer@live.cn` ����ûǮ�����˳���лл��λ��


## ������

```javascript
  var info = {
    nickName  : "qiujuer",
    site : "http://www.qiujuer.net"
  }
```


License
--------

    Copyright 2014 CengaLabs.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
