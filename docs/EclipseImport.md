# Eclipse Import

## ��

�����������������ң� **Eclipse** �������ô����ʹ�ÿؼ�����������ֻ��˵��Ǹ�ˣ�

����� **Android Studio** ��ֻ��Ҫ���뱾�� `aar` ���߲���Զ�̵ķ�ʽ��һ�д�����ܸ㶨��Ҳ����Ҫ�Լ�дȨ�޺����á�

������Ϊ `aar` ���а����� `Jar,jni,aidl,AndroidManifest,assets,res,R.java` ��Щ��һ�������� **Library** .

���� **Eclipse** ��ͨ������һ�������ǵ��� `Jar` �������¶��ˣ���Ȼ�� Jar �а����˴󲿷ֵĴ��룬�������������Ҫ��Դ�����������Ϊ���ˣ�����Ҫʹ�ÿؼ��ͱ����Լ������������֡�


## Jar

������������ţ�û�����Ѳ���İɣ�
�򵥵�˵������ **Jar** �ļ��� **Eclipse** ����Ŀ `Libs` �ļ����¡�
Ȼ������Ŀ�а�����ȥ��OK��

�������� **Jar** ������£�����ʹ�������� `Util` ���� `App` ���еķ��� ��


## JNI

����ĵ�����ʵ�� **Jar** ���ơ�

������������ȫƽ̨�� `so` �ļ�������Կ��� `eclipse\libs` �ļ��е����Լ���Ŀ�� `libs` �С�

�������� `Jni so` �ļ��������ڿ���ʹ�� `App` ���е� `BlurKit` ����ģ�����ͼƬ�ˣ���Ȼû�е��������£���Ҳ�ǿ���ʹ�� `BlurKit` �е� `Java` ������ģ�����ͼƬ��


## aidl

ʹ�� `Command` ��������Ľӿڡ� `Command` ���ǲ��õĶ������̷���ģʽ����Ҫʹ�� `aidl` �ӿ����������ݡ�
�������������һ�ٵ�����ʲô����Ϊ��ӿ��Ѿ������ `Jar` ���ˣ������ʵ����Ҫ���ã�
* ��ô���������Ŀ�н��� `aidl` 
* �������½�������`net.qiujuer.genius.command`
* Ȼ���ڴ˰��½����ļ� ��`ICommandInterface.aidl`
* ���д����룺

 ```java

    // ICommandInterface.aidl
    package net.qiujuer.genius.command;

    // Declare any non-default types here with import statements

    interface ICommandInterface {
        String command(String id, int timeout, String params);
        void cancel(String id);
        int getTaskCount();
    }

 ```

��ʱ�㻹����ʹ�� `Command` ģ�飬��Ϊ������ `CommandService` ��������á�


## AndroidManifest

����һ������Ҫ�������Ŀ `AndroidManifest` �ļ���
##### Ȩ��

```xml
    <!-- ���� Ȩ�� -->
    <uses-permission android:name="android.permission.INTERNET" />
    <!-- ��־д�ļ� Ȩ�� -->
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
    <!-- getDeviceId Ȩ�� -->
    <uses-permission android:name="android.permission.READ_PHONE_STATE"/>
    
```

##### CommandService

```xml

    <application android:allowBackup="true">
        <service
            android:name="net.qiujuer.genius.command.CommandService"
            android:enabled="true"
            android:exported="false"
            android:process="net.qiujuer.genius.command.CommandService">
            <intent-filter>
                <action android:name="net.qiujuer.genius.command.ICommandInterface" />
            </intent-filter>
        </service>
    </application>

```

����������������������ʹ�� `Command` �� `net tool` ģ���ˡ�


## assets

��һ���У�������Ŀ��Ŀ¼ `eclipse/assets` �е������ļ������Լ���Ŀ�е� `assets` �ļ����С�
����Ϊ����֧�� `material` ģ���пؼ�������������׼����


## res

����һ���У�����Ҫ������Ŀ��Ŀ¼ `eclipse/res/values` �е� `xml` �ļ������Լ���Ŀ�е� `res/value` �ļ����С�
����Ϊ����֧�� `material` ģ���пؼ�����ɫ�Լ����Ե������ļ���


## R.java

�������һ���ˣ��ܶ���ǰ�涼����ˣ�����Ψ����һ��û����������ʹ�ÿؼ���ʱ����� `����` ����ʧ�ܡ�
����һ���У�����Ҫ����������
* �������Ŀ���ҵ� `gen` Ŀ¼
* �����½������� `net.qiujuer.genius`
* ������Ŀ¼ `eclipse/R.java` �ļ����������İ��С�


�����������Ŀ������ʹ�����а���ˣ������ؼ���顣��Ȼ�������Ҫˢ��һ�������Ŀ��


## Resource

[`Release Files`](Release)


## Picture

![Picture](https://raw.githubusercontent.com/qiujuer/Genius-Android/resource/images/global/AE414EAE.png)


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
