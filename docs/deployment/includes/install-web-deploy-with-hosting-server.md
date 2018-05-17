Barındırma sunucuları için Web dağıtımı 3.6 UI yayımlama ayarları dosyasından oluşturulmasını sağlamak ek yapılandırma özelliklerini sağlar.

1. Web dağıtımı Windows sunucuda zaten yüklü 3.6 varsa, kullanarak kaldırma **Denetim Masası** > **programları** > **ProgramKaldır**.

2. Ardından, Windows Server üzerinde barındırma sunucuları için Web dağıtımı 3.6 yükleyin.

    Barındırma sunucuları için Web Dağıtımı'nı yüklemek için kullanın [Web Platformu Yükleyicisi (Webpı)](https://www.microsoft.com/web/downloads/platform.aspx). (Web Platformu yükleyicisi bağlantı IIS'den bulmak için seçin **IIS** Sunucu Yöneticisi'nin sol bölmesinde. Sunucuya sağ tıklayın ve seçin **Internet Information Services (IIS) Yöneticisi'ni**.)

    Web Platformu Yükleyicisi'nde bulduğunuz **Web dağıtımı barındıran sunucular için** uygulama sekmesinde.

3. Windows Server'da Git **sunucu rollerini seçin** > **Web sunucusu (IIS)** > **Yönetim Araçları**ve ardından **IIS Yönetim betikleri ve araçları** rolü tıklatın **sonraki**ve ardından rolü yükleyin.

    ![IIS Yönetim betikleri ve araçları yükleyin](../../deployment/media/tutorial-iis-management-scripts-and-tools.png)

    Bu rol, yayımlama ayarları dosyası oluşturmayı etkinleştirmek için gereklidir.

4. Web dağıtımı doğru açarak çalıştığından emin olun **Denetim Masası > Sistem ve Güvenlik > Yönetim Araçları > Hizmetler** emin olun **Web Dağıtım Aracı hizmeti** çalıştıran ( Hizmet adı eski sürümlerinde farklıdır).

    Aracı hizmeti çalışmıyorsa başlatın. Hiç yoksa, Git **Denetim Masası > Programlar > program Kaldır**, bulma **Microsoft Web dağıtımı <version>** . Tercih **değişiklik** yükleme ve, seçtiğinizden emin olun **yerel sabit sürücüye yüklenecek** Web dağıtımı bileşenleri için. Değişikliği yükleme adımlarını tamamlayın.