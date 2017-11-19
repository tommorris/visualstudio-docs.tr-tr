---
title: "Eski dil hizmeti gezinti çubuğunda desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Navigation bar, supporting in language services [managed package framework]
- language services [managed package framework], Navigation bar
ms.assetid: 2d301ee6-4523-4b82-aedb-be43f352978e
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 935ea7d9fde2872c952f79afaa95058e9f18d0a7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="support-for-the-navigation-bar-in-a-legacy-language-service"></a>Eski dil hizmeti gezinti çubuğunda desteği
Gezinti Çubuğu Düzenleyicisi görünüm üstündeki türleri ve üyeleri dosyasında görüntüler. Sol açılan türleri gösterilir ve üyeleri sağındaki açılan gösterilir. Kullanıcı türü seçtiğinde şapka türü ilk satırında yerleştirilir. Kullanıcı bir üye seçtiğinde şapka üye tanımını yerleştirilir. Aşağı açılan kutuları şapka geçerli konumunu yansıtacak şekilde güncelleştirilir.  
  
## <a name="displaying-and-updating-the-navigation-bar"></a>Görüntüleme ve gezinti çubuğu güncelleştiriliyor  
 Gezinti çubuğu desteklemek için öğesinden bir sınıf türetin <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> sınıfı ve uygulamanıza <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> yöntemi. Dil hizmetiniz bir kod penceresinde, temel verilen zaman <xref:Microsoft.VisualStudio.Package.LanguageService> sınıfı başlatır <xref:Microsoft.VisualStudio.Package.CodeWindowManager>, içeren <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> kod penceresi temsil eden nesne. <xref:Microsoft.VisualStudio.Package.CodeWindowManager> Nesne sonra verilen yeni bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> nesnesi. <xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A> Yöntemi alır bir <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> nesnesi. Örneği döndürürse, <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> sınıfı, <xref:Microsoft.VisualStudio.Package.CodeWindowManager> çağrıları, <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> iç doldurmak için yöntem listeler ve geçirir, <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> nesnesine [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Yöneticisi çubuğu açılır. Aşağı açılan Yöneticisi, sırasıyla çağırır <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.SetDropdownBar%2A> yöntemi, <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> kurmak için nesne <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBar> iki açılan çubukları içeren nesne.  
  
 Şapka taşındığında <xref:Microsoft.VisualStudio.Package.LanguageService.OnIdle%2A> yöntem çağrılarını <xref:Microsoft.VisualStudio.Package.LanguageService.OnCaretMoved%2A> yöntemi. Temel <xref:Microsoft.VisualStudio.Package.LanguageService.OnCaretMoved%2A> yöntem çağrılarını <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> yönteminde, <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> gezinti çubuğunda durumunu güncelleştirmek için sınıf. Bir dizi geçirdiğiniz <xref:Microsoft.VisualStudio.Package.DropDownMember> bu yöntem nesnelere. Her nesne açılan bir girişe temsil eder.  
  
## <a name="the-contents-of-the-navigation-bar"></a>Gezinti çubuğu içeriğini  
 Gezinti çubuğu genellikle türlerinin bir listesini ve üyelerin listesini içerir. Türlerinin bir listesini geçerli kaynak dosyasında kullanılabilen tüm türleri içerir. Tür adları, tam ad alanı bilgileri içerir. C# kod iki tür ile bir örnek verilmiştir:  
  
```csharp  
namespace TestLanguagePackage  
{  
    public class TestLanguageService  
    {  
        internal struct Token  
        {  
            int tokenID;  
        }  
        private Tokens[] tokens;  
        private string serviceName;  
    }  
}  
```  
  
 Tür listesi görüntülenir `TestLanguagePackage.TestLanguageService` ve `TestLanguagePackage.TestLanguageService.Tokens`.  
  
 Üye listesi türleri listede seçilen türü kullanılabilir üyelerini görüntüler. Yukarıdaki kod örneği, kullanarak `TestLanguagePackage.TestLanguageService` seçili türüdür üye listesi özel üyeler içerir `tokens` ve `serviceName`. İç yapısı `Token` görüntülenmez.  
  
 Düzeltme işareti içinde yerleştirildiğinde üyenin adını kalın yapmak için üye listesi uygulayabilirsiniz. Üyeleri de metin gri şapka şu anda nereye konumlandırılır kapsamında olmadıklarını belirten görüntülenebilir.  
  
## <a name="enabling-support-for-the-navigation-bar"></a>Gezinti çubuğu desteğini etkinleştirme  
 Gezinti çubuğu desteğini etkinleştirmek için ayarlamanız gerekir `ShowDropdownBarOption` parametresinin <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> özniteliğini `true`. Bu parametre ayarlar <xref:Microsoft.VisualStudio.Package.LanguagePreferences.ShowNavigationBar%2A> özelliği. Gezinti çubuğu desteklemek için uygulamanız gereken <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> nesnesinde <xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A> yöntemi <xref:Microsoft.VisualStudio.Package.LanguageService> sınıfı.  
  
 Uygulamanızda <xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A> yöntemi, varsa <xref:Microsoft.VisualStudio.Package.LanguagePreferences.ShowNavigationBar%2A> özelliği ayarlanmış `true`, geri dönebilirsiniz bir <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> nesnesi. Nesne döndürmezse gezinti çubuğu görüntülenmez.  
  
 Düzenleyici görünüm açıkken sıfırlamak bu denetim için mümkün olması için gezinti çubuğunu göster seçeneğini kullanıcı tarafından ayarlanmış olabilir. Kullanıcı kapatın ve değişiklik gerçekleşmeden önce Düzenleyicisi penceresini yeniden açın.  
  
## <a name="implementing-support-for-the-navigation-bar"></a>Gezinti Çubuğu uygulama desteği  
 <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> Yöntemi iki liste (her açılan için bir) ve her listesindeki geçerli seçim temsil eden iki değerlerini alır. Listeler ve seçim değerleri, bu durumda güncelleştirilebilir <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> yöntemi döndürmelidir `true` listeler değişmiş belirtmek için.  
  
 Seçimi türleri açılan değiştikçe üye listesi yeni türü yansıtacak şekilde güncelleştirilmesi gerekir. Üyeler listesinde gösterilen birini kullanabilir:  
  
-   Geçerli türü için üyelerin listesi.  
  
-   Tüm üyeler kullanılabilir kaynak dosya, ancak geçerli türü değil, tüm üyeleri grileştirilmiş metin olarak görüntülenir. Kullanıcı Hızlı gezinme için kullanılabilir ancak bunlar şu anda seçili türü parçası olmadığını rengi gösterir şekilde grileştirilmiş üyeleri seçebilirsiniz.  
  
 Uygulaması <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> yöntemi tipik olarak aşağıdaki adımları gerçekleştirir:  
  
1.  Kaynak dosya için geçerli bildirimleri listesini alın.  
  
     Bir listeler doldurmak için çeşitli yöntemler vardır. Bir yaklaşım ise özel bir yöntem, sürümünde oluşturmak için <xref:Microsoft.VisualStudio.Package.LanguageService> çağırır sınıfı <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> yöntemi bir özel ayrıştırma sebeple tüm bildirimleri listesini döndürür. Çağırmak için başka bir yaklaşım olabilir <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> yöntemi doğrudan <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> özel ayrıştırma sebeple yöntemi. Bildirimler önbelleğe almak için üçüncü bir yaklaşım olabilir <xref:Microsoft.VisualStudio.Package.AuthoringScope> son tam ayrıştırma işlemi tarafından döndürülen sınıfı <xref:Microsoft.VisualStudio.Package.LanguageService> değerinden almanıza ve sınıf <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> yöntemi.  
  
2.  Doldurmak veya türlerinin bir listesini güncelleştirin.  
  
     Kaynak değiştiğinde veya geçerli düzeltme işareti konumuna bağlı türleri metin stilini değiştirmek seçmiş olmanız durumunda güncelleştirilecek türleri listesi içeriğini olabilir. Bu konum için geçirilen Not <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> yöntemi.  
  
3.  Geçerli düzeltme işareti konumuna bağlı türleri listesinde seçmek için türünü belirler.  
  
     Geçerli düzeltme konumu barındırır türü bulmak için 1. adımda edinilen bildirimleri arayın ve türleri listesi türleri listesine dizinini belirlemek bu tür için arama yapın.  
  
4.  Doldurmak veya seçili türüne göre üyelerin listesini güncelleştirin.  
  
     Üye listesi içinde görüntülenenleri yansıtır **üyeleri** açılır. Üye listesi içeriğini kaynak değişirse veya yalnızca seçilen tür üyeleri görüntüleme ve seçili türü değiştirildi güncelleştirilmesi gerekebilir. Kaynak dosyasında tüm üyeleri görüntülemek seçerseniz, listedeki her bir üyesinin metin stili oluşturma, şu anda seçili türünün değiştirilmesi durumunda güncelleştirilmesi gerekiyor.  
  
5.  Geçerli düzeltme işareti konumuna bağlı üye listesi seçmek için üye belirler.  
  
     Geçerli düzeltme konumu içeren üye için 1. adımda edinilen bildirimleri arama sonra üye listesi üye listesine dizinini belirlemek bu üye için arama yapın.  
  
6.  Dönüş `true` listeleri ya da listesinde yapılan seçimleri için herhangi bir değişiklik yapılıp yapılmadığını.