---
title: Tür Üyeleri Oluşturma ve Yapılandırma (Sınıf Tasarımcısı)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.classdetails.method
- vs.classdetails.property
- vs.classdetails.parameter
- vs.classdetails.event
- vs.classdetails.field
helpviewer_keywords:
- Class Designer [Visual Studio], member creation
- type members, modifying in Class Designer
- parameters [ASP.NET Web Services], adding to methods
- type members, configuring
- type members
- members
- type members, creating
- members, creating
- Class Designer [Visual Studio], type members
- read-only information, displaying
- members, configuring
- methods [Visual Studio], adding parameters
- Class Details window
- Class Details window, member creation
ms.assetid: 42af8738-3738-4ca7-82ff-edf573a68f96
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ce62e2d2723c38d933c9efc4c8d910ac418dcb4f
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="creating-and-configuring-type-members-class-designer"></a>Oluşturma ve yapılandırma türü üyeleri (Sınıf Tasarımcısı)
Bu üyelerin bir sınıf türlerine Diyagram ve bu üyeler yapılandırma ekleyebilirsiniz **sınıfı ayrıntıları** penceresi:

|**Türü**|**Üyeleri oluşabilir**|
|--------------|--------------------------------|
|örneği|yöntem, özellik (C# ve Visual Basic için), alan, olay (C# ve Visual Basic için), oluşturucu (yöntem), yıkıcı (yöntem), sabit|
|Enum|üye|
|Arabirim|yöntem, özellik, olay (C# ve Visual Basic için)|
|Soyut Sınıf|yöntem, özellik (C# ve Visual Basic için), alan, olay (C# ve Visual Basic için), oluşturucu (yöntem), yıkıcı (yöntem), sabit|
|Yapı (C# için Struct)|yöntem, özellik (C# ve Visual Basic için), alan, olay (C# ve Visual Basic için), oluşturucu (yöntem), yıkıcı (yöntem), sabit|
|Temsilci|parametre|
|Modül (Yalnızca VB)|yöntem, özellik, alan, olay, oluşturucu, sabit|

> [!NOTE]
> Bir özelliğin get ve set erişimcileri ek mantığa gerek duymadığında, otomatik uygulanan özellikleri (yalnızca C#) kullanarak özellik bildirimini daha kısa yapın. Gelen tam imza göstermek için **sınıf diyagramı** menüsünü seçin **değişiklik üyeleri biçimi** > **görüntü tam imza**. Otomatik uygulanan özellikler hakkında daha fazla bilgi için bkz: [Auto-Implemented özellikleri](/dotnet/csharp/programming-guide/classes-and-structs/auto-implemented-properties).

## <a name="common-tasks"></a>Ortak görevler

|Görev|İçeriği destekleme|
|----------|------------------------|
|**Kullanmaya başlama:** oluşturmak ve tür üyeleri yapılandırmadan önce açmalısınız **sınıfı ayrıntıları** penceresi.|-   [Sınıf Ayrıntıları penceresi açın](creating-and-configuring-type-members.md#open-the-class-details-window)<br />-   [Sınıf ayrıntıları kullanım notları](creating-and-configuring-type-members.md#class-details-usage-notes)<br />-   [Salt okunur bilgileri görüntüleme](creating-and-configuring-type-members.md#display-of-read-only-information)<br />-   [Sınıf diyagramında ve sınıf Ayrıntıları penceresinde klavye ve Fare kısayolları](keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window.md)|
|**Oluşturma ve tür üyeleri değiştirme:** yeni üyeler oluşturmak, üyeleri değiştirmek ve kullanarak bir yönteme parametre ekleme **sınıfı ayrıntıları** penceresi.|-   [Üye oluşturma](creating-and-configuring-type-members.md#create-members)<br />-   [Tür üyeleri değiştirme](creating-and-configuring-type-members.md#modify-type-members)<br />-   [Yönteme parametre ekleme](creating-and-configuring-type-members.md#add-parameters-to-methods)|

## <a name="open-the-class-details-window"></a>Sınıf Ayrıntıları penceresi açın
Varsayılan olarak, **sınıfı ayrıntıları** yeni bir sınıf diyagramı açtığınızda penceresi otomatik olarak görüntülenir (bkz [nasıl yapılır: projelere sınıf diyagramları ekleme](how-to-add-class-diagrams-to-projects.md)). Ayrıca açabilirsiniz **sınıfı ayrıntıları** penceresi açık olarak, aşağıdaki yollarla.

#### <a name="to-open-the-class-details-window"></a>Sınıf Ayrıntıları penceresini açmak için

1.  Bir bağlam menüsü görüntülemek için diyagramdaki herhangi bir sınıf üzerinde sağ tıklayın.

2.  Bağlam menüsünde tıklatın **sınıfı ayrıntıları**.

 - veya -

-   İşaret **diğer pencereler** Görünüm menüsünde ve ardından **sınıfı ayrıntıları**.

## <a name="create-members"></a>Üye oluşturma
Üye oluşturmak için aşağıdaki araçlardan herhangi birini kullanabilirsiniz:

-   **Sınıf Tasarımcısı**

-   **Sınıf ayrıntıları** penceresi araç

-   **Sınıf ayrıntıları** penceresi

> [!NOTE]
> Bu bölümdeki yordamları kullanarak oluşturucular ve yıkıcılar da oluşturabilirsiniz. Lütfen oluşturucular ve Yıkıcılar yöntemleri özel türde olduğundan ve bu nedenle, göründükleri olun unutmayın ayı **yöntemleri** bölme sınıf diyagramı şekilleri hem de **yöntemleri** bölümü **Sınıf ayrıntıları** penceresi kılavuz.

> [!NOTE]
> Bir temsilciye ekleyebileceğiniz tek varlık parametredir. Yordam başlıklı Not ' kullanarak bir üye oluşturmak için **sınıfı ayrıntıları** penceresi araç ' Bu eylem için geçerli değil.

#### <a name="to-create-a-member-using-class-designer"></a>Sınıf Tasarımcısı'nı kullanarak üye oluşturmak için

1.  Üye eklemek için işaret istediğiniz türüne sağ **Ekle**ve ardından eklemek istediğiniz üyenin türünü seçin.

     Yeni bir üye imzası oluşturulur ve türe eklenir. İçinde değiştirebileceğiniz bir varsayılan adı verilen **Sınıf Tasarımcısı**, **sınıfı ayrıntıları** penceresinde veya **özellikleri** penceresi.

2.  İsteğe bağlı olarak, üyeyle ilgili diğer ayrıntıları (örneğin, türü) belirtin.

#### <a name="to-create-a-member-using-the-class-details-window-toolbar"></a>Sınıf Ayrıntıları penceresi araç kullanarak bir üye oluşturmak için

1.  Diyagram yüzeyinde, üye eklemek istediğiniz türü seçin.

     Odağı türü alır ve içeriğini görüntülenen **sınıfı ayrıntıları** penceresi.

2.  İçinde **sınıfı ayrıntıları** penceresi araç, üst simgesine tıklayın ve seçin **yeni \<üye >** açılan listeden.

     İmleç taşır **adı** eklemek istediğiniz üye türü için bir satır alanındaki. Örneğin tıkladıysanız **yeni özellik**, yeni bir satırda imleci taşır **özellikleri** bölümünü **sınıfı ayrıntıları** penceresi.

3.  Oluşturmak istediğiniz üyenin adını yazın ve Enter'a basın (ya da başka bir şekilde, örneğin, Sekme tuşuna basarak odağı taşıyın).

     Yeni bir üye imzası oluşturulur ve türe eklenir. Üye şimdi kodda var ve görüntülenen **Sınıf Tasarımcısı**, **sınıfı ayrıntıları** penceresi ve Özellikler penceresini.

4.  İsteğe bağlı olarak, üyeyle ilgili diğer ayrıntıları (örneğin, türü) belirtin.

#### <a name="to-create-a-member-using-the-class-details-window"></a>Sınıf Ayrıntıları penceresi kullanarak bir üye oluşturmak için

1.  Diyagram yüzeyinde, üye eklemek istediğiniz türü seçin.

     Odağı türü alır ve içeriğini görüntülenen **sınıfı ayrıntıları** penceresi.

2.  İçinde **sınıfı ayrıntıları** penceresinde üye eklemek istediğiniz türünü içeren bölümün tıklatın  **\<Üye Ekle >**. Örneğin, bir alan eklemek istiyorsanız, tıklatın  **\<alanını ekleyin >**.

3.  Oluşturmak istediğiniz üyenin adını yazın ve Enter'a basın.

     Yeni bir üye imzası oluşturulur ve türe eklenir. Üye şimdi kodda var ve görüntülenen **Sınıf Tasarımcısı**, **sınıfı ayrıntıları** penceresi ve Özellikler penceresini.

4.  İsteğe bağlı olarak, üyeyle ilgili diğer ayrıntıları (örneğin, türü) belirtin.

     **Not:** üyeleri oluşturmak üzere klavye kısayollarını kullanabilirsiniz. Daha fazla bilgi için bkz: [klavye ve Fare kısayolları sınıf diyagramında ve sınıf Ayrıntıları penceresinde](keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window.md).

## <a name="modify-type-members"></a>Tür üyeleri değiştirme
Sınıf Tasarımcısı, diyagram görüntülenen türlerin üyelerinde değişiklik yapmanıza olanak sağlar. Sınıf diyagramında görüntülenen ve salt okunur olmayan her türün üyelerini değiştirebilirsiniz. Özellikler penceresi tasarım yüzeyi yerinde düzenleme kullanarak tür üyeleri değiştirme ve **sınıfı ayrıntıları** penceresi.

Görüntülenen tüm üyeleri **sınıfı ayrıntıları** pencere türleri sınıf diyagramında üyeleri temsil eder. Dört üye türü vardır: yöntemler, özellikler, alanlar ve olaylar.

Tüm üye satırları, üyeleri türe göre gruplandıran başlıkların altında görünür. Örneğin, tüm özellikler başlığı altında görünür **özellikleri**, kılavuz, bir düğüm olarak hangi bulunabilir daraltılmış veya genişletilmiş.

Her üye satırı aşağıdaki öğeleri görüntüler:

-   **Üye simgesi**

     Her üyü türü kendi simgesiyle gösterilir. Fare üyenin imza görüntülenecek üye simgesine işaret edin. Satırı seçmek için, üye simgesine ya da üye simgesinin solundaki boşluğa tıklayın.

-   **Üye adı**

     **Adı** üye satır sütununda üyenin adını görüntüler. Bu ad ayrıca görüntülenen **adı** Özellikleri penceresinde özelliği. Okuma/Yazma izinlerine sahip herhangi bir üyenin adını değiştirmek için bu hücreyi kullanın.

     Varsa **adı** sütundur fare üye adına işaret eden, adın tamamını görüntüler tüm ad göstermek için çok dar.

-   **Üye türü**

     **MemberType** hücre kullanan IntelliSense, geçerli projenin veya başvurulan projeleri mevcut tüm türleri listesinden seçmenizi sağlar.

-   **Üye değiştiricisi**

     Üyenin görünürlük değiştiricisi ya da değiştirme `Public` (`public`), `Private` (`private`), `Friend` (`internal`) `Protected` (`protected`), `Protected``Friend` (`protected``internal`), ya da `Default`.

-   **\<üye ekleme >**

     Son satırında **sınıfı ayrıntıları** penceresi metnini içeren  **\<Üye Ekle >** içinde **adı** hücre. Bu hücreye tıklarsanız yeni bir üye oluşturabilirsiniz. Daha fazla bilgi için bkz: [üyeleri oluşturmak](creating-and-configuring-type-members.md#create-members).

-   **Özellikleri penceresinde üye özellikleri**

     **Sınıfı ayrıntıları** penceresi Özellikler penceresinde görüntülenen üye özellikleri kümesini görüntüler. Özelliğin bir konumda değiştirilmesi, özelliğin değerini global olarak güncelleştirir. Değerinin diğer konumda görüntülenmesi de buna dahildir.

-   **Özet**

     **Özet** hücre üye hakkında bilgilerin özetini gösterir. İçinde üç nokta düğmesine **Özet** görüntülemek veya hakkında bilgi düzenlemek için hücre **Özet**, **dönüş türü**, ve **açıklamalar** üyesi için .

-   **Gizle**

     Zaman **Gizle** onay kutusu seçiliyse, üye türünde görüntülenmez.

#### <a name="to-modify-a-type-member"></a>Bir tür üyesini değiştirmek için

1.  Sınıf Tasarımcısı'nı kullanarak bir tür seçin.

2.  Varsa **sınıfı ayrıntıları** penceresi görüntülenmez, tıklatın **sınıfı ayrıntıları** Sınıf Tasarımcısı araç çubuğunda penceresi.

3.  Alanlarının değerleri Düzenle **sınıfı ayrıntıları** penceresi kılavuz. Her düzenlemeden sonra ENTER'a basın ya da bir başka yolla, örneğin SEKME tuşuna basarak, odağı düzenlenen alanın dışına taşıyın. Düzenlemeleriniz anında koda yansır.

    > [!NOTE]
    >  Bir üyenin yalnızca adını değiştirmek istiyorsanız, bunu yerinde düzenlemeyi kullanarak yapabilirsiniz.

## <a name="add-parameters-to-methods"></a>Yönteme parametre ekleme
Parametreleri kullanarak yöntemlere ekleme **sınıfı ayrıntıları** penceresi. Parametreler, zorunlu veya isteğe bağlı olacak şekilde yapılandırılabilir. İçin bir değer sağlama **isteğe bağlı varsayılan** özelliği bir parametrenin isteğe bağlı bir parametre olarak kodu oluşturmak için tasarımcı bildirir.

Parametre satırı aşağıdaki öğeleri içerir:

-   **Ad**

     **Adı** bir parametre satır sütununda parametresi adını görüntüler. Bu ad ayrıca görüntülenen **adı** Özellikleri penceresinde özelliği. Okuma/Yazma izinlerine sahip herhangi bir parametrenin adını değiştirmek için bu hücreyi kullanabilirsiniz.

     Parametre adına işaret eden görüntüler parametresinin adı **adı** sütundur adın tamamını göstermek için çok dar.

-   **Türü**

     **Parametre türü** hücre geçerli projenin veya başvurulan projeleri kullanılabilir türler listesinden seçmenize olanak tanır IntelliSense kullanır.

-   **Değiştirici**

     **Değiştiricisi** parametresi satırda hücre kabul eder ve new değiştiricisi parametresinin görüntüler. Yeni bir parametresi değiştiricisi girmek için seçmek için aşağı açılan liste kutusunu kullanın **hiçbiri**, **ref**, **çıkışı**, veya **params** C# ve **ByVal**, **ByRef**, veya **ParamArray** vb'deki

-   **Özet**

     **Özet** parametresi satırda hücre verir parametresi kod düzenleyicisine girerken IntelliSense içinde görünen kodu açıklama girme.

-   **\<parametre ekleme >**

     Üyenin son parametre satır metni içeren **<add parameter>** içinde **adı** hücre. Bu hücreye tıklanması yeni bir parametre oluşturmanıza izin verir. Daha fazla bilgi için bkz: [bir yönteme parametre eklemek için](creating-and-configuring-type-members.md#add-parameters-to-methods).

**Özellikleri penceresinde parametresi özellikleri**

Özellikler penceresi görüntülenen aynı parametre özellikleri görüntüler **sınıfı ayrıntıları** penceresi: **adı**, **türü**, **değiştiricisi** , **Özet**, yanı sıra **isteğe bağlı varsayılan** özelliği. Özelliğin bir konumda değiştirilmesi, özelliğin değerini global olarak güncelleştirir (değerinin diğer konumda görüntülenmesi de buna dahildir).

> [!NOTE]
> Bir parametre için bir temsilci eklemek için bkz [üyeleri oluşturmak](creating-and-configuring-type-members.md#create-members).


> [!NOTE]
> Yıkıcı üyesi bir yöntem olmasına karşın, parametrelere sahip olamaz.


### <a name="to-add-a-parameter-to-a-method"></a>Bir yönteme parametre eklemek için

1.  Diyagram yüzeyinde, parametre eklemek istediğiniz yöntemi içeren türe tıklayın.

     Odağı türü alır ve içeriğini görüntülemek **sınıfı ayrıntıları** penceresi.

2.  İçinde **sınıfı ayrıntıları** penceresinde, bir parametre eklemek istediğiniz yöntemi satırının genişletin.

     Yalnızca bir çift ayraç ve sözcükler içeren bir girintili parametresi satır görünür  **\<parametresini ekleyin >.**

3.  Tıklatın  **\<parametresini ekleyin >**, yeni bir parametre ve tuşuna adını yazın **Enter**.

     Yeni bir parametre, yöntemi ve yöntemin kod olarak eklenir. Bu görüntüler **sınıfı ayrıntıları** ve özellikleri penceresinde.

4.  İsteğe bağlı olarak, parametreyle ilgili diğer ayrıntıları (örneğin, türü) belirtin.

### <a name="to-add-an-optional-parameter-to-a-method"></a>Bir yönteme isteğe bağlı parametre eklemek için

1.  Diyagram yüzeyinde, isteğe bağlı parametre eklemek istediğiniz yöntemi içeren türe tıklayın.

     Odağı türü alır ve içeriğini görüntülemek **sınıfı ayrıntıları** penceresi.

2.  İçinde **sınıfı ayrıntıları** penceresinde, isteğe bağlı bir parametre eklemek istediğiniz yöntemi satırının genişletin.

     Yalnızca bir çift ayraç ve sözcükler içeren bir girintili parametresi satır görünür  **\<parametresini ekleyin >.**

3.  Tıklatın  **\<parametresini ekleyin >**, yeni bir parametre ve tuşuna adını yazın **Enter**.

     Yeni bir parametre, yöntemi ve yöntemin kod olarak eklenir. Bu görüntüler **sınıfı ayrıntıları** ve özellikleri penceresinde.

4.  Özellikler penceresi için bir değer yazın **isteğe bağlı varsayılan** özelliği. Bir parametrenin İsteğe Bağlı Varsayılan özelliği ayarlandığında bu parametre isteğe bağlı olur.

    > [!NOTE]
    >  İsteğe bağlı parametreler, parametre listesindeki en son parametreler olmalıdır.

## <a name="class-details-usage-notes"></a>Sınıf ayrıntıları kullanım notları
Lütfen kullanmak için aşağıdaki ipuçlarını Not **sınıfı ayrıntıları** penceresi.

**Düzenlenebilir ve düzenlenemeyen hücreleri**

Tüm hücreleri **sınıfı ayrıntıları** penceresi birkaç istisna dışında düzenlenebilir:

-   Tüm türü salt okunur olduğunda, örneğin, başvurulan bütünleştirilmiş kodunda yer alıyor. Sınıf Tasarımcısı'nda şekli seçtiğinizde **sınıfı ayrıntıları** penceresi bir salt okunur durumda ayrıntılarını görüntüler.

-   Dizin oluşturucular için, ad bilgisi salt okunur ve geri kalanı (tür, değiştirici, özet) düzenlenebilir özelliktedir.

-   Tüm genel türler salt okunur parametrelere sahip **sınıfı ayrıntıları** penceresi. Bir genel parametreyi değiştirmek için kaynak kodunu düzenleyin.

-   Genel türde tanımlanan tür parametresinin adı salt okunurdur.

-   Bir tür kod (ayrıştırılamayan), bozuk olduğunda **sınıfı ayrıntıları** penceresi, salt okunur olarak tür içeriğini görüntüler.

**Sınıf Ayrıntıları penceresi ve kaynak kodu**

-   Kaynak kodu bir şekli sağ tıklatarak görüntüleyebileceğiniz **sınıfı ayrıntıları** penceresi (veya Sınıf Tasarımcısı) kod Görüntüle'ye tıklayın. Kaynak kodu dosyası açılır ve seçili öğeye kadar ilerler.

-   Kaynak kodu değiştirme hemen yansıtılır imza bilgilerini Sınıf Tasarımcısı'nda görüntülenir ve **sınıfı ayrıntıları** penceresi. Varsa **sınıfı ayrıntıları** zaman penceresi kapatıldığında, yeni bilgiler, onu bir sonraki açışınızda görülebilir.

-   Bir tür kod (ayrıştırılamayan), bozuk olduğunda **sınıfı ayrıntıları** penceresi, salt okunur olarak tür içeriğini görüntüler.

**Sınıf Ayrıntıları penceresinde Pano işlevi**

 Kopyalama veya kesme alanları veya satırları **sınıfı ayrıntıları** penceresi ve başka bir türe yapıştırın. Bir satırı ancak salt okunur ise kesebilirsiniz. Satır yapıştırdığınız zaman **sınıfı ayrıntıları** penceresi çakışmayı önlemek için (kopyalanan satırın adından türetilen) yeni bir ad atar.

## <a name="display-of-read-only-information"></a>Salt okunur bilgileri görüntüleme
Sınıf Tasarımcısı ve **sınıfı ayrıntıları** pencere türleri (ve türlerini üyeleri) için aşağıdakileri görüntüleyebilirsiniz:

-   Sınıf diyagramı içeren bir proje

-   Sınıf diyagramı içeren bir projeden başvurulan proje

-   Sınıf diyagramı içeren bir projeden başvurulan derleme

Sonraki iki durum için, başvurulan varlık (bir tür veya üye) temsil ettiği sınıf diyagramında salt okunurdur.

Bir projenin tamamı ya da kısımları (tek tek dosyalar gibi) salt okunur olabilir. Projenin veya dosyalarından birinin salt okunur olduğu en yaygın durumlar, bir kaynak kodu denetiminin altında olduğu (ve kullanıma alınmamış), bir dış derlemede var olduğu veya işletim sisteminin dosyaları salt okunur olarak düşündüğü durumlardır.

**Kaynak kodu denetimi**

Sınıf Tasarımcısı'nda yaptığınız değişiklikleri kaydetmek için projeyi kontrol etmeniz sınıf diyagramında bir proje dosyası olarak kaydedildiğinden veya **sınıfı ayrıntıları** penceresi.

**Salt okunur projeleri**

Proje, kaynak kodu denetimi dışındaki bir nedenle salt okunur olabilir. Proje kapatma proje dosyanın üzerine yazmak için (kaydetme) değişiklikleri atmak mı yoksa soran bir iletişim kutusu görüntüler veya kapatma işlemini iptal eder. Üzerine yazmayı tercih ederseniz proje dosyalarının üzerine yazılır ve okuma/yazma özellikli yapılırlar. Yeni sınıf diyagramı dosyası eklenir.

**Salt okunur türleri**

Kaynak kodu dosyasının salt okunur bir türü içeren bir proje kaydetmeye çalışırken **salt okunur dosya salt okunur** iletişim kutusu görüntülenirse, hangi dosyayı altında yeni bir ad veya yeni bir konuma kaydedin veya salt okunur dosyanın üzerine yazmak için seçenekler sunar . Dosyanın üzerine yazarsanız yeni kopyası artık salt okunur özellikte olmaz.

Bir Kod dosyası sözdizimi hatası içeriyorsa, bu dosyadaki kodu gösteren şekiller söz dizimi hatası düzeltilinceye kadar geçici olarak salt okunur olur. Bu durumdaki şekiller, "Kaynak kodu dosyası ayrıştırma hatası içeriyor" yazılı araç ipucunu gösteren kırmızı bir metin ve kırmızı bir simge görüntüler.

Başka bir proje düğümü altında ya da başvurulan bir derleme düğümü altında bulunan bir başvurulan tür (.NET Framework türü gibi), Sınıf Tasarımcısı'nın tasarım yüzeyinde salt okunur olarak belirtilir. Açık durumda bulunan projede var olan bir yerel tür okuma/yazma özelliklidir ve Sınıf Tasarımcısı'nın tasarım yüzeyindeki şekli de böyle belirtilir.

Dizin oluşturucular okuma-yazma kodda ve **sınıfı ayrıntıları** penceresi, ancak dizin oluşturucu adı salt okunur.

Sınıf Tasarımcısı kullanarak kısmi yöntemler düzenleyemezsiniz veya **sınıfı ayrıntıları** penceresi; bunları düzenlemek için Kod Düzenleyicisi'ni kullanmanız gerekir.

Sınıf Tasarımcısı kullanarak yerel C++ kodunu düzenleyemezsiniz veya **sınıfı ayrıntıları** penceresi; yerel C++ kod düzenlemek için Kod Düzenleyicisi'ni kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

- [Türleri ve ilişkilendirmeleri görüntüleme](viewing-types-and-relationships.md)
- [Sınıfları ve türleri yeniden düzenleme](refactoring-classes-and-types.md)