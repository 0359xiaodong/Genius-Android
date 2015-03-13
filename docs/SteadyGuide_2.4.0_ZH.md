## Version 2.4.0 Guide

[`����`](SteadyGuide_2.4.0_ZH) [`English`](SteadyGuide_2.4.0) [`Guides`](GuideCatalog) [`Sample`](https://raw.githubusercontent.com/qiujuer/Genius-Android/resource/release/simple-steady_2.4.0.apk)


## Genius-Android��ʲô?

![icon](https://raw.githubusercontent.com/qiujuer/Genius-Android/resource/images/second/62EA232A.png)

**Genius-Android** �� **Android** ��һЩ���õĵķ�������, **Genius** �ṩ6��������飺

* `app` (**Ui**)
* `animation` ��**����**��
* `widget` ��**Material�ؼ�**��
* `command` ��**������**��
* `net tool` ��**Ping��Dns...**��
* `util` ��**���÷���,��**��


## ��ͼ

##### GeniusUI

###### CheckBox
![GeniusUI](https://raw.githubusercontent.com/qiujuer/Genius-Android/resource/images/second/64633441.gif)

###### Button
![GeniusUI](https://raw.githubusercontent.com/qiujuer/Genius-Android/resource/images/second/D8320195.gif)

###### EditText
![GeniusUI](https://raw.githubusercontent.com/qiujuer/Genius-Android/resource/images/second/E34FB6E8.gif)

###### SeekBar
![GeniusUI](https://raw.githubusercontent.com/qiujuer/Genius-Android/resource/images/second/6B2FACAC.gif)

##### BlurKit
![BlurKit](https://raw.githubusercontent.com/qiujuer/Genius-Android/resource/images/second/20505B1D.png)

##### ThemeColors
![ThemeColors](https://raw.githubusercontent.com/qiujuer/Genius-Android/resource/images/second/AA31BFB4.png)

###### All
![GeniusUI](https://raw.githubusercontent.com/qiujuer/Genius-Android/resource/images/second/172755E3.png)


## ����ģ��

* `app`
  > *  `UIKit` ֧�����߳�`ͬ��`��`�첽`�л������̲߳���
  > *  `BlurKit` ֧��`Java`��`Jni`ʹ��`StackBlur`�㷨ģ��ͼƬ

* `animation`
  > *  `TouchEffectAnimator` ֧�ֿ�����Ӧ�����Ч
  > *  `TouchEffectEnum` Press, Move, Ripple, Ease, None

* `widget`
  > *  ���� `opensans` `roboto`
  > *  ��ɫ `none` `dark` `darker` `light`
  > *  �ؼ� `GeniusButton` `GeniusCheckBox` `GeniusTextView` `GeniusEditText` `GeniusSeekBar`

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
  > *  `Tools` `ID` `SN` ȷ���豸Ψһ��ʶ
  > *  `Log` ��ϵͳLogһ��ʹ�ü򵥣�һ������
  > *  `Log` �ɴ洢��־���ļ�������������
  > *  `Log` ������¼����������������ʾ��־��Ϣ
  > *  `FixedList` �������У��Զ����������ֶ�������


## ��ȡ��

* `Star` �� `Fork` ��Ŀ��
* `MavenCentral` Զ�̵��� :

```gradle
// ����Ŀ "build.gradle" �����
dependencies {
  compile 'com.github.qiujuer:genius:2.4.0'
}

```


## ������־

* �汾��`2.4.0`
* ���ڣ�`2015-03-02`
* ��־��[`������־`](SteadyNotes_2.X)


## ʹ�÷���

##### ��ʼ��������

```java
Genius.initialize(Application application);
Genius.dispose();

```


##### `widget` ģ��

```xml
// �����ڸ�������ָ����
<LinearLayout
    ...
    xmlns:genius="http://schemas.android.com/apk/res-auto"/>

// ������ʽ������ͼColors
// �ṩ���壺`opensans` `roboto`
// �����ϸ��`bold` `extrabold` `extralight` `light` `regular`

// ==================ȫ������==================
<net.qiujuer.genius.widget.all
    ...
    genius:g_textAppearance="light"
    genius:g_fontFamily="opensans"
    genius:g_fontWeight="bold"
    genius:g_fontExtension="ttf"
    genius:g_borderWidth="5dp"
    genius:g_theme="@array/StrawberryIce"
    genius:g_cornerRadius="5dp"
    genius:g_cornerRadii_A="10dp"
    genius:g_cornerRadii_B="10dp"
    genius:g_cornerRadii_C="10dp"
    genius:g_cornerRadii_D="10dp" />

// `g_textAppearance`: ָ��������ɫ��Ĭ��Ϊ `none`
// `g_fontFamily`: ָ�����������е�һ������
// `g_fontWeight`: ָ�������ϸ
// `g_fontExtension`: ������չ��
// `g_borderWidth`: ��߿��
// `g_theme`: ָ��������ʽ��17������ѡ
// `g_cornerRadius`: �ؼ���ԵԲ�ǰ뾶,Ĭ��Ϊ `0`
// `g_cornerRadii`: �ؼ���Ե�Ľ�(A,B,C,D)�뾶,Ĭ��Ϊ `0`

// ==================GeniusButton==================
<net.qiujuer.genius.widget.GeniusButton
    ...
    genius:g_delayClick="true"
    genius:g_touchEffect="move"
    genius:g_touchEffectColor="#ff4181ff"
    genius:g_blockButtonEffectHeight="10dp" />

// `g_delayClick`: �Ƿ��ӳ���Ӧ����¼���Ĭ��Ϊ"True"
// `g_touchEffect`: press, move, ease, ripple, none
// `g_touchEffectColor`: ��ɢЧ����ɫ, `g_touchEffect`Ϊ"None"����Ч
// `g_blockButtonEffectHeight`: �ײ���Ӱ�߶�

// ==================GeniusCheckBox==================
<net.qiujuer.genius.widget.GeniusCheckBox
    ...
    genius:g_ringWidth="2dp"
    genius:g_circleRadius="22dp"
    genius:g_checked="true"
    genius:g_enabled="true" />

// `g_ringWidth`: Բ�����
// `g_circleRadius`: Բ�İ뾶
// `g_checked`: �Ƿ�ѡ��
// `g_enabled`: �Ƿ�ɵ��
//  ע�⣺�����������Բ������ɫ������Ե���Attributes�ķ���setColors��
//  ͬʱ���� Attribute.notifyAttributeChange() �������и���

// ==================GeniusTextView==================
<net.qiujuer.genius.widget.GeniusTextView
    ...
    genius:g_textColor="light"
    genius:g_backgroundColor="dark"
    genius:g_customBackgroundColor="#FFFFFF" />

// `g_textColor`: ������ɫ����
// `g_backgroundColor`: ������ɫ����
// `g_customBackgroundColor`: ������ɫ

// ==================GeniusEditText==================
<net.qiujuer.genius.widget.GeniusEditText
    ...
    genius:g_fieldStyle="fill"
    genius:g_showTitle="true"
    genius:g_titleTextColor="#ff1fedff|statusColor"
    genius:g_titleTextSize="12sp"
    genius:g_titlePaddingTop="5dp"
    genius:g_titlePaddingLeft="5dp" />

// `g_fieldStyle`: �����ʽ��`fill` `box` `transparent` `line`
// `g_showTitle`: �Ƿ���ʾHint Title
// `g_titleTextColor`: Title ������ɫ
// `g_titleTextSize`: Title �����С
// `g_titlePaddingTop`: Title �������
// `g_titlePaddingLeft`: Title ��߼��

// ==================GeniusSeekBar==================
<net.qiujuer.genius.widget.GeniusSeekBar
    ...
    genius:g_min="0"
    genius:g_max="100"
    genius:g_value="0"
    genius:g_tickSize="0dp"
    genius:g_thumbSize="6dp"
    genius:g_touchSize="12dp"
    genius:g_trackStroke="2dp"
    genius:g_scrubberStroke="4dp"
    genius:g_rippleColor="@color/color_value"
    genius:g_scrubberColor="@color/color_value"
    genius:g_trackColor="@color/color_value"
    genius:g_thumbColor="@color/color_value"
    genius:g_indicatorBackgroundColor="@color/color_value"
    genius:g_indicatorFormatter="%04d"
    genius:g_indicatorTextAppearance="@style/DefaultBalloonMarkerTextAppearanceStyle"
    genius:g_allowTrackClickToDrag="true"/>

// `g_indicatorBackgroundColor`: �������ݱ�Ǳ���ɫ
// `g_indicatorFormatter`: ����������ʾ int ֵ�� Formatter
// `g_indicatorTextAppearance`: ��������������ʽ
// `g_allowTrackClickToDrag`: �����ڿؼ����ⲿλ�϶���Ĭ�ϣ�True

```

```java
// ͨ������ı�����
GeniusCheckBox box = new GeniusCheckBox(this);
box.setChecked(!box.isChecked());
// Theme
CheckBoxAttributes attr = box.getAttributes();
attr.setRingWidth(4);
attr.setCircleRadius(22);
attr.setTheme(R.array.StrawberryIce, getResources());
// ������ɫ��ͨ������������ߵ�������
// �ֱ��� Darker, Dark, Primary, Light, Translucence, Transparent
attr.setColors(new int[]{
               Color.parseColor("#ffc26165"), Color.parseColor("#ffdb6e77"),
               Color.parseColor("#ffef7e8b"), Color.parseColor("#fff7c2c8"),
               Color.parseColor("#ffc2cbcb"), Color.parseColor("#ffe2e7e7")});
// ��������
attr.notifyAttributeChange();

```


##### `app` ģ��

```java
// "Runnable" ʵ������ "run()" ����
// "run()" ���������߳��У��������н��н������
// ͬ���������߳�,�ȴ����̴߳�����ɺ����ִ�����߳�
UIKit.runOnMainThreadSync(Runnable runnable);
// �첽�������߳�,����ȴ�
UIKit.runOnMainThreadAsync(Runnable runnable);
// ͬ���������߳�ֻ�ȴ�ָ��ʱ��
// @param runnable Runnable �ӿ�
// @param waitTime ���̵߳ȴ�ʱ��
// @param cancel   �ȴ�ʱ�䵽ʱ�Ƿ�ȡ�����߳�ִ�и�����
UIKit.runOnMainThreadSync(Runnable runnable, int waitTime, boolean cancel)

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


##### `animation` ģ��

```java
// TouchEffectAnimator �������Ŀؼ���ӵ����Ч
// ��Ч���ͣ�Press, Move, Ease, Ripple, None
public class GeniusButton extends Button {
    private TouchEffectAnimator touchEffectAnimator = null;
    // ����Ŀؼ��г�ʼ������Ч����
    public void initTouchEffect(TouchEffect touchEffect) {
        touchEffectAnimator = new TouchEffectAnimator(this);
        // ����ģʽ
        touchEffectAnimator.setTouchEffect(touchEffect);
        // ������ɫ
        touchEffectAnimator.setEffectColor("color");
        // ��ԵԲ���뾶
        touchEffectAnimator.setClipRadius(20);
        // ͬ�ϣ���ָ�������ǣ��ĸ����㣩�Ļ���
        touchEffectAnimator.setClipRadii(new float[]{20,20,20,20,20,20,20,20});
        // ���ö���ʱ�䱶�������ö���ģʽ�����
        touchEffectAnimator.setAnimDurationFactor(1);
    }
    // �ӳٵ���¼�(��ѡ)
    @Override
    public boolean performClick() {
        if (touchEffectAnimator != null) {
            return !touchEffectAnimator.interceptClick() && super.performClick();
        } else
            return super.performClick();
    }
    // �ص����Ʒ���
    @Override
    protected void onDraw(Canvas canvas) {
        if (touchEffectAnimator != null)
            touchEffectAnimator.onDraw(canvas);
        super.onDraw(canvas);
    }
    // ��������¼�
    @Override
    public boolean onTouchEvent(MotionEvent event) {
        if (touchEffectAnimator != null)
            touchEffectAnimator.onTouchEvent(event);
        return super.onTouchEvent(event);
    }
}

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


// ====================HashUtils==================
// ��ϣ���㣨Md5��
// �ɼ����ַ������ļ�Md5ֵ

// ��ȡ�ַ���MD5
String hash = HashUtils.getMD5String(String str);
// ��ȡ�ļ�MD5
String hash = HashUtils.getMD5String(File file);


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

[`Eclipse`](EclipseImport) ���޷�ֱ�ӵ�����Ŀ�����Ƚ���һ����Ŀ���ն�ӦĿ¼��������Ŀ�С�


## ����

��ʹ�������κ����⣬��ӭ�ܼ�ʱ�������ң�������������ϵ��ʽ���ҽ���

* ��Ŀ��[`�ύBug���뷨`](https://github.com/qiujuer/Genius-Android/issues)
* �ʼ���[`qiujuer@live.cn`](mailto:qiujuer@live.cn)
* QQ�� `756069544`
* QQȺ��[`387403637`](http://shang.qq.com/wpa/qunwpa?idkey=3f1ed8e41ed84b07775ca593032c5d956fbd8c3320ce94817bace00549d58a8f)
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

    Copyright 2014-2015 Qiujuer.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.