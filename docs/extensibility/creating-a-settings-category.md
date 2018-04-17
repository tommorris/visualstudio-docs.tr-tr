---
title: Ayarları kategorisi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- profile settings, creating categories
ms.assetid: 97c88693-05ff-499e-8c43-352ee073dcb7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 22a625466dd8a94ba1dbe67ef6f05bec68954d2c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-settings-category"></a>Ayarları kategorisi oluşturma
Bu kılavuzda bir Visual Studio ayarları kategori oluşturmak ve değerlerini kaydetmek ve değerleri ayarları dosyasından geri yüklemek için kullanın. Ayarları kategorisi "özel ayarları noktası"; görünür ilgili özellikleri grubudur. diğer bir deyişle, bir onay kutusu olarak **içeri ve dışarı aktarma ayarları** Sihirbazı. (Üzerinde Bul **Araçları** menü.) Ayarları kaydedilmez veya kategori olarak geri ve tek tek ayarların Sihirbazı'nda görüntülenmez. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
 Buradan türetme ayarları kategorisi oluşturma <xref:Microsoft.VisualStudio.Shell.DialogPage> sınıfı.  
  
 Bu kılavuzda başlatmak için önce ilk bölümü tamamlamalısınız [Seçenekleri sayfası oluşturma](../extensibility/creating-an-options-page.md). Sonuçta elde edilen Seçenekleri Özellik Kılavuzu inceleyin ve kategorideki özellikleri değiştirmenize olanak sağlar. Özellik kategori ayarları dosyasında kaydettikten sonra özellik değerlerinin nasıl depolandığını görmek için dosyasını inceleyin.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-settings-category"></a>Ayarları kategorisi oluşturma  
 Bu bölümde, kaydetme ve geri yükleme ayarları kategorisi değerleri için özel ayarlar noktası kullanın.  
  
#### <a name="to-create-a-settings-category"></a>Ayarları kategori oluşturmak için  
  
1.  Tamamlamak [Seçenekleri sayfası oluşturma](../extensibility/creating-an-options-page.md).  
  
2.  VSPackage.resx dosyasını açın ve bu üç dize kaynaklarını ekleyin:  
  
    |Ad|Değer|  
    |----------|-----------|  
    |106|My kategorisi|  
    |107|Ayarlarım|  
    |108|OptionInteger ve OptionFloat|  
  
     Bu kaynaklar "My kategori" kategori adı, nesne "My ayarlarını" ve "OptionInteger ve OptionFloat" kategorisi açıklaması oluşturur.  
  
    > [!NOTE]
    >  Bu üç, yalnızca kategori adı içeri ve dışarı aktarma ayarları Sihirbazı'nda görünmez.  
  
3.  MyToolsOptionsPackage.cs içinde eklemek bir `float` adlı özellik `OptionFloat` için `OptionPageGrid` aşağıdaki örnekte gösterildiği gibi sınıfı.  
  
    ```csharp  
    public class OptionPageGrid : DialogPage  
    {  
        private int optionInt = 256;  
        private float optionFloat = 3.14F;  
  
        [Category("My Options")]  
        [DisplayName("My Integer option")]  
        [Description("My integer option")]  
        public int OptionInteger  
        {  
            get { return optionInt; }  
            set { optionInt = value; }  
        }  
        [Category("My Options")]  
        [DisplayName("My Float option")]  
        [Description("My float option")]  
        public float OptionFloat  
        {  
            get { return optionFloat; }  
            set { optionFloat = value; }  
        }  
    }  
    ```  
  
    > [!NOTE]
    >  `OptionPageGrid` Kategori adı "My kategori" Şimdi iki özelliklerini oluşur `OptionInteger` ve `OptionFloat`.  
  
4.  Ekleme bir <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> için `MyToolsOptionsPackage` sınıfı ve "My kategori" CategoryName verin, "My ayarları" ObjectName verin ve isToolsOptionPage true olarak ayarlayın. CategoryResourceID, objectNameResourceID ve DescriptionResourceID kimlikleri daha önce oluşturduğunuz karşılık gelen dize kaynağı ayarlayın.  
  
    ```csharp  
    [ProvideProfileAttribute(typeof(OptionPageGrid),   
        "My Category", "My Settings", 106, 107, isToolsOptionPage:true, DescriptionResourceID = 108)]  
    ```  
  
5.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneğinde, görmelisiniz **kılavuz sayfam** şimdi tamsayı ve kayan nokta değerlerine sahip.  
  
## <a name="examining-the-settings-file"></a>Ayarlar dosyası inceleniyor  
 Bu bölümde, özellik kategori değerlerini ayarları dosyasına aktarın. Dosyasını inceleyin ve özellik kategoriye değerleri içeri aktarın.  
  
1.  Projeyi hata ayıklama modunda F5 tuşuna basarak başlatın. Bu Deneysel bir örneğini başlatır.  
  
2.  Açık **Araçlar / Seçenekler** iletişim.  
  
3.  Sol bölmede ağaç görünümünde genişletin **My kategori** ve ardından **kılavuz sayfam**.  
  
4.  Değerini değiştirme **OptionFloat** 3.1416 için ve **OptionInteger** 12. **Tamam**'ı tıklatın.  
  
5.  Üzerinde **Araçları** menüsünde tıklatın **içeri ve dışarı aktarma ayarları**.  
  
     **İçeri ve dışarı aktarma ayarları** Sihirbazı görünür.  
  
6.  Emin olun **verme seçili ortam ayarları** seçilir ve ardından **sonraki**.  
  
     **Dışarı aktarma ayarları Seç** sayfası görüntülenir.  
  
7.  Tıklatın **ayarlarımı**.  
  
     **Açıklama** değişikliklerini **OptionInteger ve OptionFloat**.  
  
8.  Olduğundan emin olun **My ayarları** seçilir ve ardından yalnızca kategori **sonraki**.  
  
     **Ayarları dosyanızın adını** sayfası görüntülenir.  
  
9. Yeni ayarları dosya adı `MySettings.vssettings` ve uygun bir dizine kaydedin. **Son**'a tıklayın.  
  
     **Verme tam** Raporları Sayfası, ayarlarınızı başarıyla dışarı aktarıldı.  
  
10. Üzerinde **dosya** menüsündeki **açık**ve ardından **dosya**. Bulun `MySettings.vssettings` ve açın.  
  
     (Sizin GUID'ler farklılık gösterir) dosyası aşağıdaki bölümde verilen özelliği kategori bulabilirsiniz.  
  
    ```  
    <Category name="My Category_My Settings"   
          Category="{4802bc3e-3d9d-4591-8201-23d1a05216a6}"   
          Package="{6bb6942e-014c-489e-a612-a935680f703d}"   
          RegisteredName="My Category_My Settings">  
          PackageName="MyToolsOptionsPackage">  
       <PropertyValue name="OptionFloat">3.1416</PropertyValue>   
       <PropertyValue name="OptionInteger">12</PropertyValue>   
    </Category>  
    ```  
  
     Tam kategori adı alt çizgi ve nesne adından kategori adı için ek tarafından biçimlendirildiğinden dikkat edin. Dışarı aktarılan değerlerine birlikte kategorisinde OptionFloat ve OptionInteger görünür.  
  
11. Değiştirmeden ayarları dosyasını kapatın.  
  
12. Üzerinde **Araçları** menüsünde tıklatın **seçenekleri**, genişletin **My kategori**, tıklatın **kılavuz sayfam** ve değerini değiştirmek  **OptionFloat** 1.0 için ve **OptionInteger** 1. **Tamam**'ı tıklatın.  
  
13. Üzerinde **Araçları** menüsünde tıklatın **içeri ve dışarı aktarma ayarları**seçin **seçili ortam ayarları**ve ardından **sonraki**.  
  
     **Geçerli ayarları Kaydet** sayfası görüntülenir.  
  
14. Seçin **Hayır, yalnızca yeni ayarları Al** ve ardından **sonraki**.  
  
     **Seçin, koleksiyon ayarlarını içeri aktarmak için** sayfası görüntülenir.  
  
15. Seçin `MySettings.vssettings` dosyasını **My ayarları** ağaç görünümü düğümünün. Dosya ağaç görünümünde görünmüyorsa tıklatın **Gözat** ve bulun. **İleri**'ye tıklayın.  
  
     **Seçin ayarları içeri aktarmak için** iletişim kutusu görüntülenir.  
  
16. Olduğundan emin olun **My ayarları** seçilir ve ardından **son**. Zaman **alma tam** sayfası görüntülendikten sonra **Kapat**.  
  
17. Üzerinde **Araçları** menüsünde tıklatın **seçenekleri**, genişletin **My kategori**, tıklatın **kılavuz sayfam** ve özellik kategori değerlerine sahip olduğunu doğrulayın geri.