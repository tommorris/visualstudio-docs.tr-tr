
1. Güncelleştirilmiş yapılandırma seçenekleri kullanıcı Arabiriminde göstermek için IIS Yönetim Konsolu kapatıp yeniden açın.

1. IIS, sağ **varsayılan Web sitesi**, seçin **dağıtma** > **yapılandırma Web dağıtımı yayımlama**.

    ![Web dağıtımı yapılandırma yapılandırma](../../deployment/media/tutorial-configure-web-deploy-publishing.png)

1. İçinde **yapılandırma Web dağıtımı yayımlama** iletişim kutusunda, ayarları inceleyin.

1. Tıklatın **Kurulum**.

    İçinde **sonuçları** paneli, erişim haklarını çıktısında belirtilen kullanıcı ve, verilen bir dosyayı bir *.publishsettings* dosya uzantısı, iletişim kutusunda gösterilen konumda oluşturuldu bir kutu.

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <publishData>
      <publishProfile
        publishUrl="https://myhostname:8172/msdeploy.axd"
        msdeploySite="Default Web Site"
        destinationAppUrl="http://myhostname:80/"
        mySQLDBConnectionString=""
        SQLServerDBConnectionString=""
        profileName="Default Settings"
        publishMethod="MSDeploy"
        userName="myhostname\myusername" />
    </publishData>
    ```

    Windows Server ve IIS yapılandırmasına bağlı olarak farklı değerler XML dosyasına bakın. Birkaç ayrıntılarını gördüğünüz değerleri şunlardır:

    * *Msdeploy.axd* başvurulan dosya `publishUrl` Web dağıtımı için dinamik olarak üretilen bir HTTP işleyicisini dosya bir özniteliktir. (Test amacıyla, `http://myhostname:8172` genellikle de çalışır.)
    * `publishUrl` Bağlantı noktası, Web dağıtımı için varsayılan olmayan bağlantı noktası 8172, ayarlanır.
    * `destinationAppUrl` Bağlantı noktası, IIS için varsayılan bağlantı noktası 80 ' olarak ayarlanmış.
    * Visual Studio'da (daha sonraki adımlarda) konak adını kullanarak uzak ana bilgisayara bağlanmak erişemiyorsanız ana bilgisayar adı yerine IP adresi sınayın.

    > [!NOTE]
    > Bir Azure VM'de çalışan IIS yayımlıyorsa, ağ güvenlik grubu listesinde Web dağıtımı ve IIS bağlantı noktalarının açmanız gerekir. Ayrıntılı bilgi için bkz: [yükleme ve çalıştırma IIS](/azure/virtual-machines/windows/quick-create-portal#open-port-80-for-web-traffic).

1. Bu dosyayı Visual Studio çalıştırdığınız bilgisayara kopyalayın.
