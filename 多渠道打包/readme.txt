
app build.gradle
	buildTypes {
        release {
            // ������־Log �����ӡ
            buildConfigField("boolean", "enableLog", "false")
            //����
            minifyEnabled false
            //Zipalign�Ż�
            zipAlignEnabled true
            // �Ƴ����õ�resource�ļ�
            shrinkResources true
            //ǰһ���ִ���ϵͳĬ�ϵ�android����Ļ����ļ������ļ��Ѿ������˻����Ļ�������
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
        }
    }
    /*���������*/
    productFlavors {
        wandoujia {}
        baidu {}
        c360 {}
        uc {}
    }
    //��������
    productFlavors.all { flavor ->
        flavor.manifestPlaceholders = [UMENG_CHANNEL_VALUE: name]
    }