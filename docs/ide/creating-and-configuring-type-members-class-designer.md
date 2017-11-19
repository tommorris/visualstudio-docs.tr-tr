---
title: "Tür üyeleri (Sınıf Tasarımcısı) yapılandırma ve oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d720df18b817e838cd3e5e0e34c9a7e123c1a402
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-and-configuring-type-members-class-designer"></a>Tür Üyeleri Oluşturma ve Yapılandırma (Sınıf Tasarımcısı)
Bu üyelerin bir sınıf türlerine Diyagram ve bu üyeler yapılandırma ekleyebilirsiniz **sınıfı ayrıntıları** penceresi:  
  
|**Türü**|**Üyeleri oluşabilir**|  
|--------------|--------------------------------|  
|örneği|yöntem, özellik (C# ve Visual Basic için), alan, olay (C# ve Visual Basic için), oluşturucu (yöntem), yıkıcı (yöntem), sabit|  
|Enum|üye|  
|Arabirim|yöntem, özellik, olay (C# ve Visual Basic için)|  
|Soyut Sınıf|yöntem, özellik (C# ve Visual Basic için), alan, olay (C# ve Visual Basic için), oluşturucu (yöntem), yıkıcı (yöntem), sabit|  
|Yapı (C# için Struct)|yöntem, özellik (C# ve Visual Basic için), alan, olay (C# ve Visual Basic için), oluşturucu (yöntem), yıkıcı (yöntem), sabit|  
|Temsilci|Parametre|  
|Modül (Yalnızca VB)|yöntem, özellik, alan, olay, oluşturucu, sabit|  
  
> [!NOTE]
>  Bir özelliğin get ve set erişimcileri ek mantığa gerek duymadığında, otomatik uygulanan özellikleri (yalnızca C#) kullanarak özellik bildirimini daha kısa yapın. Gelen tam imza göstermek için **sınıf diyagramı** menüsünde seçin **değişiklik üyeleri biçimi**, **görüntü tam imza**. Otomatik uygulanan özellikler hakkında daha fazla bilgi için bkz: [Auto-Implemented özellikleri](/dotnet/csharp/programming-guide/classes-and-structs/auto-implemented-properties).  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|Destekleyici İçerik|  
|----------|------------------------|  
|**Kullanmaya başlama:** oluşturmak ve tür üyeleri yapılandırmadan önce sınıf Ayrıntıları penceresi açmanız gerekir.|-   [Sınıf Ayrıntıları penceresinde açma](../ide/creating-and-configuring-type-members-class-designer.md#OpenClassDetails)<br />-   [Kullanım notları sınıf ayrıntıları](../ide/creating-and-configuring-type-members-class-designer.md#ClassDetailsUsageNotes)<br />-   [Salt okunur bilgileri görüntüleme](../ide/creating-and-configuring-type-members-class-designer.md#ReadOnlyInfo)<br />-   [Klavye ve Fare kısayolları sınıf diyagramında ve sınıf Ayrıntıları penceresinde (Sınıf Tasarımcısı)](../ide/keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer.md)|  
|**Oluşturma ve tür üyeleri değiştirme:** yeni üyeler oluşturmak, üyeleri değiştirmek ve sınıf Ayrıntıları penceresi kullanarak bir yöntem parametreleri ekleyin.|-   [Üye oluşturma](../ide/creating-and-configuring-type-members-class-designer.md#CreateMembers)<br />-   [Tür üyeleri değiştirme](../ide/creating-and-configuring-type-members-class-designer.md#ModifyTypeMembers)<br />-   [Yönteme parametre ekleme](../ide/creating-and-configuring-type-members-class-designer.md#AddMethodParams)|  
  
##  <a name="OpenClassDetails"></a>Sınıf Ayrıntıları penceresinde açma  
 Varsayılan olarak, yeni bir sınıf diyagramı açtığınızda sınıf Ayrıntıları penceresi otomatik olarak görünür. (bkz [nasıl yapılır: sınıf diyagramları ekleme projelerine (Sınıf Tasarımcısı)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md)). Ayrıca, aşağıdaki yollarla, Sınıf Ayrıntıları penceresini doğrudan da açabilirsiniz.  
  
#### <a name="to-open-the-class-details-window"></a>Sınıf Ayrıntıları penceresini açmak için  
  
1.  Bir bağlam menüsü görüntülemek için diyagramdaki herhangi bir sınıf üzerinde sağ tıklayın.  
  
2.  Bağlam menüsünde tıklatın **sınıf Ayrıntıları penceresinde**.  
  
 - veya -  
  
-   İşaret **diğer pencereler** Görünüm menüsünde ve ardından **sınıfı ayrıntıları**.  
  
##  <a name="CreateMembers"></a>Üye oluşturma  
 Üye oluşturmak için aşağıdaki araçlardan herhangi birini kullanabilirsiniz:  
  
-   Sınıf Tasarımcısı  
  
-   Sınıf Ayrıntıları penceresi araç çubuğu  
  
-   Sınıf Ayrıntıları penceresi  
  
> [!NOTE]
>  Bu bölümdeki yordamları kullanarak oluşturucular ve yıkıcılar da oluşturabilirsiniz. Lütfen oluşturucular ve Yıkıcılar yöntemleri özel türde olduğundan ve bu nedenle, göründükleri olun unutmayın size aittir **yöntemleri** bölme sınıf diyagramı şekilleri hem de **yöntemleri** sınıfının bölümü Ayrıntılar pencere Kılavuzu.  
  
> [!NOTE]
>  Bir temsilciye ekleyebileceğiniz tek varlık parametredir. 'Sınıf Ayrıntıları Penceresi araç çubuğunu kullanarak üye oluşturmak için' başlıklı yordamın bu eylem için geçerli olmadığını unutmayın.  
  
#### <a name="to-create-a-member-using-class-designer"></a>Sınıf Tasarımcısı'nı kullanarak üye oluşturmak için  
  
1.  Üye eklemek için işaret istediğiniz türüne sağ **Ekle**ve ardından eklemek istediğiniz üyenin türünü seçin.  
  
     Yeni bir üye imzası oluşturulur ve türe eklenir. İçinde değiştirebileceğiniz bir varsayılan adı verilen **Sınıf Tasarımcısı**, **sınıfı ayrıntıları** penceresinde veya **özellikleri** penceresi.  
  
2.  İsteğe bağlı olarak, üyeyle ilgili diğer ayrıntıları (örneğin, türü) belirtin.  
  
#### <a name="to-create-a-member-using-the-class-details-window-toolbar"></a>Sınıf Ayrıntıları Penceresi araç çubuğunu kullanarak üye oluşturmak için  
  
1.  Diyagram yüzeyinde, üye eklemek istediğiniz türü seçin.  
  
     Tür odağa gelir ve içeriği Sınıf Ayrıntıları penceresinde görüntülenir.  
  
2.  Sınıf Ayrıntıları penceresi araç çubuğunda, üst simgesine tıklayın ve seçin **yeni \<üye >** açılan listeden.  
  
     İmleç taşır **adı** eklemek istediğiniz üye türü için bir satır alanındaki. Örneğin tıkladıysanız **yeni özellik**, imleci yeni bir satırda taşır **özellikleri** sınıf Ayrıntıları penceresi bölümü.  
  
3.  Oluşturmak istediğiniz üyenin adını yazın ve Enter'a basın (ya da başka bir şekilde, örneğin, Sekme tuşuna basarak odağı taşıyın).  
  
     Yeni bir üye imzası oluşturulur ve türe eklenir. Üye şimdi kodda var ve görüntülenen **Sınıf Tasarımcısı**, sınıf Ayrıntıları penceresi ve Özellikler penceresini.  
  
4.  İsteğe bağlı olarak, üyeyle ilgili diğer ayrıntıları (örneğin, türü) belirtin.  
  
#### <a name="to-create-a-member-using-the-class-details-window"></a>Sınıf Ayrıntıları Penceresini kullanarak üye oluşturmak için  
  
1.  Diyagram yüzeyinde, üye eklemek istediğiniz türü seçin.  
  
     Tür odağa gelir ve içeriği Sınıf Ayrıntıları penceresinde görüntülenir.  
  
2.  Sınıf Ayrıntıları penceresinde üye eklemek istediğiniz türünü içeren bölümün tıklatın  **\<Üye Ekle >**. Örneğin, bir alan eklemek istiyorsanız, tıklatın  **\<alanını ekleyin >**.  
  
3.  Oluşturmak istediğiniz üyenin adını yazın ve Enter'a basın.  
  
     Yeni bir üye imzası oluşturulur ve türe eklenir. Üye şimdi kodda var ve görüntülenen **Sınıf Tasarımcısı**, sınıf Ayrıntıları penceresi ve Özellikler penceresini.  
  
4.  İsteğe bağlı olarak, üyeyle ilgili diğer ayrıntıları (örneğin, türü) belirtin.  
  
     **Not:** üyeleri oluşturmak üzere klavye kısayollarını kullanabilirsiniz. Daha fazla bilgi için bkz: [klavye ve Fare kısayolları sınıf diyagramında ve sınıf Ayrıntıları penceresinde (Sınıf Tasarımcısı)](../ide/keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer.md).  
  
##  <a name="ModifyTypeMembers"></a>Tür üyeleri değiştirme  
 Sınıf Tasarımcısı, diyagram görüntülenen türlerin üyelerinde değişiklik yapmanıza olanak sağlar. Sınıf diyagramında görüntülenen ve salt okunur olmayan her türün üyelerini değiştirebilirsiniz. (Bkz [salt okunur bilgileri (Sınıf Tasarımcısı) görüntüsünü](http://msdn.microsoft.com/en-us/33e2d3a9-1668-4d10-ae56-fa09b3156e0a).) Tür üyelerini tasarım yüzeyinde, Özellikler penceresinde ve Sınıf Ayrıntıları penceresinde yerinde düzenleme yaparak değiştirirsiniz.  
  
 Sınıf Ayrıntıları penceresinde görüntülenen tüm üyeler sınıf diyagramındaki türlerin üyelerini temsil eder. Dört üye türü vardır: yöntemler, özellikler, alanlar ve olaylar.  
  
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
  
     Sınıf Ayrıntıları penceresinde son satır metni içeren  **\<Üye Ekle >** içinde **adı** hücre. Bu hücreye tıklarsanız yeni bir üye oluşturabilirsiniz. Daha fazla bilgi için bkz: [oluşturma üyeleri](../ide/creating-and-configuring-type-members-class-designer.md#CreateMembers).  
  
-   **Özellikleri penceresinde üye özellikleri**  
  
     Sınıf Ayrıntıları penceresi, Özellikler penceresinde görüntülenen üye özelliklerinin bir alt kümesini görüntüler. Özelliğin bir konumda değiştirilmesi, özelliğin değerini global olarak güncelleştirir. Değerinin diğer konumda görüntülenmesi de buna dahildir.  
  
-   **Özet**  
  
     **Özet** hücre üye hakkında bilgilerin özetini gösterir. İçinde üç nokta düğmesine **Özet** görüntülemek veya hakkında bilgi düzenlemek için hücre **Özet**, **dönüş türü**, ve **açıklamalar** üyesi için .  
  
-   **Gizle**  
  
     Zaman **Gizle** onay kutusu seçiliyse, üye türünde görüntülenmez.  
  
#### <a name="to-modify-a-type-member"></a>Bir tür üyesini değiştirmek için  
  
1.  Sınıf Tasarımcısı'nı kullanarak bir tür seçin.  
  
2.  Sınıf Ayrıntıları penceresi görüntülenmiyorsa tıklatın **sınıf Ayrıntıları penceresinde** Sınıf Tasarımcısı araç çubuğunda.  
  
3.  Sınıf Ayrıntıları penceresi kılavuzunun alanlarındaki değerleri düzenleyin. Her düzenlemeden sonra ENTER'a basın ya da bir başka yolla, örneğin SEKME tuşuna basarak, odağı düzenlenen alanın dışına taşıyın. Düzenlemeleriniz anında koda yansır.  
  
    > [!NOTE]
    >  Bir üyenin yalnızca adını değiştirmek istiyorsanız, bunu yerinde düzenlemeyi kullanarak yapabilirsiniz.  
  
##  <a name="AddMethodParams"></a>Yönteme parametre ekleme  
 Sınıf Ayrıntıları penceresini kullanarak yöntemlere parametreler ekleyin. Parametreler, zorunlu veya isteğe bağlı olacak şekilde yapılandırılabilir. İçin bir değer sağlama **isteğe bağlı varsayılan** özelliği bir parametrenin isteğe bağlı bir parametre olarak kodu oluşturmak için tasarımcı bildirir.  
  
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
  
     Üyenin son parametre satır metni içeren  **<add parameter>**  içinde **adı** hücre. Bu hücreye tıklanması yeni bir parametre oluşturmanıza izin verir. Daha fazla bilgi için bkz: [bir yönteme parametre eklemek için](../ide/creating-and-configuring-type-members-class-designer.md#HowToAddParameterToMethod).  
  
 **Özellikleri penceresinde parametresi özellikleri**  
  
 Özellikler penceresi sınıf Ayrıntıları penceresinde görüntülenen aynı parametre özellikleri görüntüler: **adı**, **türü**, **değiştiricisi**, **özeti**, yanı sıra **isteğe bağlı varsayılan** özelliği. Özelliğin bir konumda değiştirilmesi, özelliğin değerini global olarak güncelleştirir (değerinin diğer konumda görüntülenmesi de buna dahildir).  
  
> [!NOTE]
>  Bir parametre için bir temsilci eklemek için bkz [oluşturma üyeleri](../ide/creating-and-configuring-type-members-class-designer.md#CreateMembers).  
  
> [!NOTE]
>  Yıkıcı üyesi bir yöntem olmasına karşın, parametrelere sahip olamaz.  
  
###  <a name="HowToAddParameterToMethod"></a>Bir parametre için bir yöntem eklemek için  
  
1.  Diyagram yüzeyinde, parametre eklemek istediğiniz yöntemi içeren türe tıklayın.  
  
     Tür odağa gelir ve içeriği Sınıf Ayrıntıları penceresinde görüntülenir.  
  
2.  Sınıf Ayrıntıları penceresinde, parametre eklemek istediğiniz yöntemin satırını genişletin.  
  
     Yalnızca bir çift ayraç ve sözcükler içeren bir girintili parametresi satır görünür  **\<parametresini ekleyin >.**  
  
3.  Tıklatın  **\<parametresini ekleyin >**, yeni bir parametre ve tuşuna adını yazın **Enter**.  
  
     Yeni bir parametre, yöntemi ve yöntemin kod olarak eklenir. Sınıf Ayrıntıları penceresinde ve Özellikler penceresinde görünür.  
  
4.  İsteğe bağlı olarak, parametreyle ilgili diğer ayrıntıları (örneğin, türü) belirtin.  
  
### <a name="to-add-an-optional-parameter-to-a-method"></a>Bir yönteme isteğe bağlı parametre eklemek için  
  
1.  Diyagram yüzeyinde, isteğe bağlı parametre eklemek istediğiniz yöntemi içeren türe tıklayın.  
  
     Tür odağa gelir ve içeriği Sınıf Ayrıntıları penceresinde görüntülenir.  
  
2.  Sınıf Ayrıntıları penceresinde, isteğe bağlı parametre eklemek istediğiniz yöntemin satırını genişletin.  
  
     Yalnızca bir çift ayraç ve sözcükler içeren bir girintili parametresi satır görünür  **\<parametresini ekleyin >.**  
  
3.  Tıklatın  **\<parametresini ekleyin >**, yeni bir parametre ve tuşuna adını yazın **Enter**.  
  
     Yeni bir parametre, yöntemi ve yöntemin kod olarak eklenir. Sınıf Ayrıntıları penceresinde ve Özellikler penceresinde görünür.  
  
4.  Özellikler penceresi için bir değer yazın **isteğe bağlı varsayılan** özelliği. Bir parametrenin İsteğe Bağlı Varsayılan özelliği ayarlandığında bu parametre isteğe bağlı olur.  
  
    > [!NOTE]
    >  İsteğe bağlı parametreler, parametre listesindeki en son parametreler olmalıdır.  
  
##  <a name="ClassDetailsUsageNotes"></a>Kullanım notları sınıf ayrıntıları  
 Sınıf Ayrıntıları penceresinin kullanımına ilişkin aşağıdaki ipuçlarına dikkat edin.  
  
 **Düzenlenebilir ve düzenlenemeyen hücreleri**  
  
 Bir kaç özel durum dışında, Sınıf Ayrıntıları penceresindeki tüm hücreler düzenlenebilir:  
  
-   Tüm türü salt okunur olduğunda, örneğin, başvurulan bütünleştirilmiş kodunda bulunuyorsa (bkz [salt okunur bilgi görüntüleme (Sınıf Tasarımcısı)](http://msdn.microsoft.com/en-us/33e2d3a9-1668-4d10-ae56-fa09b3156e0a).) Sınıf Tasarımcısı'nda şekli seçtiğinizde, Sınıf Ayrıntıları penceresi ilgili ayrıntıları salt okunur halde görüntüler.  
  
-   Dizin oluşturucular için, ad bilgisi salt okunur ve geri kalanı (tür, değiştirici, özet) düzenlenebilir özelliktedir.  
  
-   Tüm genel öğeler Sınıf Ayrıntıları penceresinde salt okunur parametrelere sahiptir. Bir genel parametreyi değiştirmek için kaynak kodunu düzenleyin.  
  
-   Genel türde tanımlanan tür parametresinin adı salt okunurdur.  
  
-   Türün kodu bozuk (çözümlenemez) olduğunda, Sınıf Ayrıntıları penceresi türün içeriğini salt okunur olarak görüntüler.  
  
 **Sınıf Ayrıntıları penceresi ve kaynak kodu**  
  
-   Kaynak kodunu, Sınıf Ayrıntıları (veya Sınıf Tasarımcısı) penceresinde bir şekle sağ tıklayıp ardından Kodu Görüntüle'ye tıklayarak görüntüleyebilirsiniz. Kaynak kodu dosyası açılır ve seçili öğeye kadar ilerler.  
  
-   Kaynak kodunun değiştirilmesi, Sınıf Tasarımcısı ve Sınıf Ayrıntıları penceresinde imza bilgilerinin görüntüsüne anında yansıtılır. Sınıf Ayrıntıları penceresi bu sırada kapalıysa, pencereyi bir sonraki açışınızda yeni bilgiler görülür.  
  
-   Türün kodu bozuk (çözümlenemez) olduğunda, Sınıf Ayrıntıları penceresi türün içeriğini salt okunur olarak görüntüler.  
  
 **Sınıf Ayrıntıları penceresinde Pano işlevi**  
  
 Sınıf Ayrıntıları penceresinden alanları veya satırları kopyalayabilir ya da kesebilir ve bunları başka bir türe yapıştırabilirsiniz. Bir satırı ancak salt okunur ise kesebilirsiniz. Satırı yapıştırdığınızda, Sınıf Ayrıntıları penceresi çakışma olmasını önlemek için yeni bir ad (kopyalanan satırın adından türetilir) atar.  
  
##  <a name="ReadOnlyInfo"></a>Salt okunur bilgileri görüntüleme  
 Sınıf Tasarımcısı ve Sınıf Ayrıntıları penceresi aşağıdaki öğeler için türleri (ve türlerin üyelerini) görüntüleyebilir:  
  
-   Sınıf diyagramı içeren bir proje  
  
-   Sınıf diyagramı içeren bir projeden başvurulan proje  
  
-   Sınıf diyagramı içeren bir projeden başvurulan derleme  
  
 Sonraki iki durum için, başvurulan varlık (bir tür veya üye) temsil ettiği sınıf diyagramında salt okunurdur.  
  
 Bir projenin tamamı ya da kısımları (tek tek dosyalar gibi) salt okunur olabilir. Projenin veya dosyalarından birinin salt okunur olduğu en yaygın durumlar, bir kaynak kodu denetiminin altında olduğu (ve kullanıma alınmamış), bir dış derlemede var olduğu veya işletim sisteminin dosyaları salt okunur olarak düşündüğü durumlardır.  
  
 **Kaynak kodu denetimi**  
  
 Sınıf diyagramı projenin içine bir dosya olarak kaydedildiğinden, Sınıf Tasarımcısı veya Sınıf Ayrıntıları penceresinde yaptığınız değişiklikleri kaydetmek için projeyi kullanıma almanız gerekir.  
  
 **Salt okunur projeleri**  
  
 Proje, kaynak kodu denetimi dışındaki bir nedenle salt okunur olabilir. Proje kapatma proje dosyanın üzerine yazmak için (kaydetme) değişiklikleri atmak mı yoksa soran bir iletişim kutusu görüntüler veya kapatma işlemini iptal eder. Üzerine yazmayı tercih ederseniz proje dosyalarının üzerine yazılır ve okuma/yazma özellikli yapılırlar. Yeni sınıf diyagramı dosyası eklenir.  
  
 **Salt okunur türleri**  
  
 Kaynak kodu dosyasının salt okunur bir türü içeren bir proje kaydetmeye çalışırken **salt okunur dosya salt okunur** iletişim kutusu görüntülenirse, hangi dosyayı altında yeni bir ad veya yeni bir konuma kaydedin veya salt okunur dosyanın üzerine yazmak için seçenekler sunar . Dosyanın üzerine yazarsanız yeni kopyası artık salt okunur özellikte olmaz.  
  
 Bir Kod dosyası sözdizimi hatası içeriyorsa, bu dosyadaki kodu gösteren şekiller söz dizimi hatası düzeltilinceye kadar geçici olarak salt okunur olur. Bu durumdaki şekiller, "Kaynak kodu dosyası ayrıştırma hatası içeriyor" yazılı araç ipucunu gösteren kırmızı bir metin ve kırmızı bir simge görüntüler.  
  
 Başka bir proje düğümü altında ya da başvurulan bir derleme düğümü altında bulunan bir başvurulan tür (.NET Framework türü gibi), Sınıf Tasarımcısı'nın tasarım yüzeyinde salt okunur olarak belirtilir. Açık durumda bulunan projede var olan bir yerel tür okuma/yazma özelliklidir ve Sınıf Tasarımcısı'nın tasarım yüzeyindeki şekli de böyle belirtilir.  
  
 Dizin oluşturucular kod içinde ve Sınıf Ayrıntıları penceresinde okuma/yazma özelliklidir, ancak dizin oluşturucunun adı salt okunurdur.  
  
 Kısmi yöntemleri Sınıf Tasarımcısı veya Sınıf Ayrıntıları penceresini kullanarak düzenleyemezsiniz; bunları düzenlemek için Kod Düzenleyicisi'ni kullanmanız gerekir.  
  
 Yerel C++ kodunu Sınıf Tasarımcısı veya Sınıf Ayrıntıları penceresini kullanarak düzenleyemezsiniz; yerel C++ kodunu düzenlemek için Kod Düzenleyicisi'ni kullanmanız gerekir.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Görüntüleme türleri ve ilişkileri (Sınıf Tasarımcısı)](../ide/viewing-types-and-relationships-class-designer.md)|Varolan türlerinizi, üyelerinizi ve ilişkilerinizi bir sınıf diyagramında görüntüleyebilirsiniz.|  
|[Yeniden düzenleme sınıfları ve türleri (Sınıf Tasarımcısı)](../ide/refactoring-classes-and-types-class-designer.md)|Yeniden düzenlemeyi kullanarak türü ve tür üyelerini kolayca yeniden adlandırabilirsiniz. Ayrıca, sınıflar arasında üye taşıyabilir, bir sınıfı kısmi sınıflara bölebilir ve arabirimler uygulayabilirsiniz.|