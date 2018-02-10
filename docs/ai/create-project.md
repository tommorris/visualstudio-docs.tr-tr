---
---
# <a name="create-an-ai-project-from-a-template-in-visual-studio"></a>Visual Studio'da bir şablondan bir AI projesi oluşturma

Seçtiğiniz sonra [AI için Visual Studio Araçları yüklü](installation.md), şablonları, çeşitli kullanarak yeni bir AI proje oluşturmak kolaydır.

1. Visual Studio'yu başlatın.

1. Seçin **Dosya > Yeni > Proje** (Ctrl + Shift + N). İçinde **yeni proje** iletişim, arama "**AI Araçları**" ve istediğiniz şablonu seçin. Bir şablon seçerek şablonu sağlar kısa bir açıklama görüntüler unutmayın. 

    ![Python şablonuyla VS2017 yeni proje iletişim kutusu](media\create-project\new-ai-project.png)

1. Bu Hızlı Başlangıç için seçin "**TensorFlow uygulama**" Şablonu proje adı (örneğin, "MNIST") ve konum verin ve seçin **Tamam**. 

1. Visual Studio Proje dosyası oluşturur (bir `.pyproj` diskteki dosya) yanı sıra şablon tarafından açıklanan diğer dosyaları. "TensorFlow uygulama" şablonuyla proje projenizi aynı adlı bir dosya içeriyor. Dosyanın varsayılan olarak Visual Studio düzenleyicisinde açın.

    ![Python uygulama şablonu kullanırken sonuç projesi](media\create-project\new-tensorflowapp.png)

1. Bildirim kodu zaten TensorFlow, numpy, sys ve işletim sistemi dahil birkaç kitaplıkları alır. Ayrıca, uygulama hazır kolayca giriş eğitim verileri, çıktı modelleri ve günlük dosyalarının konumunu değiştirmeyi etkinleştirmek için giriş bazı bağımsız değişkenler ile başlar. Bu parametreleri işleriniz için birden çok işlem bağlamları (bir Azure dosya paylaşımı üzerindeki, yerel geliştirme kutusunda IE farklı dizin) gönderdiğinizde yararlıdır. 

1. Projenizi bu giriş parametreleri için komut satırı bağımsız değişkenleri otomatik olarak geçirerek uygulamanızın hatalarını ayıklama kolaylaştırmak için oluşturulan bazı özellikler de vardır. **Sağ tıklayın** projenizi seçip **özellikleri** 

    ![Özellikler](media\create-project\project-properties.png)

1. Tıklatın **hata ayıklama** komut dosyası değişkenleri otomatik olarak görmek için sekmesi eklenmiştir. bunları giriş verilerinizi bulunduğu ve depolanan, çıktı oluşturulacağı yeri için gerektiği gibi değiştirebilirsiniz.

    ![Özellikler](media\create-project\/project-properties_1.png)

1. Ctrl + F5 tuşuna basarak veya seçerek program Çalıştır **hata ayıklama > hata ayıklama olmadan Başlat** menüsünde. Sonuçları konsol penceresinde görüntülenir.
