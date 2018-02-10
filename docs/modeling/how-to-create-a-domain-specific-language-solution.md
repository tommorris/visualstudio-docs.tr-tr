---
title: "Nasıl yapılır: bir etki alanına özgü dil çözümü oluşturun | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
f1_keywords:
- vs.dsltools.designerwizard
helpviewer_keywords:
- Domain-Specific Language Tools, walkthroughs
- walkthroughs [Domain-Specific Language Tools], creating domain-specific language
- Domain-Specific Language Tools, creating solutions
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 5adfe90d88f46f4a3c31c1ddb6eb860403d57fe4
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-create-a-domain-specific-language-solution"></a>Nasıl yapılır: Etki Alanına Özgü Dil Çözümü Oluşturma
Bir etki alanına özgü dil (DSL) özelleştirilmiş kullanılarak oluşturulan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözümü.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu yordama başlamadan önce bu bileşenleri yüklemeniz gerekir:  
  
|||  
|-|-|  
|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]|[http://go.microsoft.com/fwlink/?LinkID=185579](http://go.microsoft.com/fwlink/?LinkID=185579)|  
|[!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]|[http://go.microsoft.com/fwlink/?LinkID=185580](http://go.microsoft.com/fwlink/?LinkID=185580)|  
|Visual Studio Görselleştirme ve modelleme SDK||  


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

  
## <a name="creating-a-domain-specific-language-solution"></a>Bir etki alanına özgü dil çözümü oluşturma  
  
#### <a name="to-create-a-domain-specific-language-solution"></a>Bir etki alanına özgü dil çözüm oluşturmak için  
  
1.  DSL Sihirbazı'nı başlatın.  
  
    1.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
    2.  **Yeni proje** iletişim kutusu görüntülenir.  
  
    3.  Altında **proje türleri**, genişletin **diğer proje türleri** düğümü ve tıklatın **genişletilebilirlik**.  
  
    4.  Tıklatın **etki alanına özgü dil Tasarımcısı**.  
  
    5.  İçinde **adı** çözüm için bir ad yazın. **Tamam**'ı tıklatın.  
  
         **Etki alanına özgü dil Tasarımcısı Sihirbazı** görüntülenir.  
  
        > [!NOTE]
        >  Tercihen, kodu oluşturmak için kullanılabilir olduğundan geçerli bir Visual C# tanımlayıcısı, yazdığınız ad olmalıdır.  
  
     ![Oluştur iletişim kutusu DSL](../modeling/media/create_dsldialog.png "Create_DSLDialog")  
  
2.  DSL şablonunu seçin.  
  
     Üzerinde **etki alanına özgü dil seçenekleri** sayfasında, çözüm şablonlarından birini gibi seçin **en az bir dil**. Oluşturmak istediğiniz DSL benzer bir şablon seçin.  
  
     Çözüm şablonları hakkında daha fazla bilgi için bkz: [bir etki alanına özgü dil çözüm şablonu seçme](../modeling/choosing-a-domain-specific-language-solution-template.md).  
  
3.  Bir dosya adı uzantısı girin **dosya uzantısı** sayfası. Bilgisayarınızın benzersiz olmalı ve DSL yüklemek istediğiniz tüm bilgisayarlarda içinde. Şu iletiyi görürsünüz **uygulamaları ya da Visual Studio Düzenleyicileri Bu uzantıyı kullanmak**.  
  
    -   Tam olarak yüklenmemiş önceki Deneysel DSL'ler içinde dosya adı uzantısı kullandıysanız, bunları dışarı kullanarak temizleyebilirsiniz **deneysel örneği sıfırlama** bulunabilir aracı [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] SDK menüsü.  
  
    -   Başka bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bu dosya uzantısı kullanır uzantısı tam olarak yüklü olduğu, bilgisayarınızda, kaldırmayı düşünün. Üzerinde **Araçları** menüsünde tıklatın **Uzantı Yöneticisi**.  
  
4.  İnceleyin ve gerekirse ayarlayın, sihirbazın diğer sayfalarını alanları. Ayarlarla memnun kaldığınızda, tıklatın **son**. Ayarlar hakkında daha fazla bilgi için bkz: [DSL Tasarımcısı sihirbaz sayfaları](#settings).  
  
     Sihirbaz adlandırıldığı iki proje bulunduğu bir çözümü oluşturur **Dsl** ve **DslPackage**.  
  
    > [!NOTE]
    >  Metin şablonları güvenilmeyen kaynaklardan çalıştırmak için tıklatın sizi uyarır olmayan bir ileti görürseniz **Tamam**. Bu ileti yeniden görünür değil ayarlayabilirsiniz.  
  
##  <a name="settings"></a>DSL Tasarımcı sihirbaz sayfaları  
 Bazı varsayılan değerlerine değişmeden alanlar bırakabilirsiniz. Ancak, dosya uzantısı alan belirlediğinizden emin olun.  
  
### <a name="solution-settings-page"></a>Çözüm Ayarları sayfası  
 **Şablonun etki alanı belirli dilinizi temel ister misiniz?**  
 Oluşturmak istediğiniz DSL benzer bir şablon seçin. Farklı şablonları uygun başlangıç noktası sağlar. Bir çözüm şablonu seçtiğinizde, sihirbaz açıklamasını görüntüler. Çözüm şablonları hakkında daha fazla bilgi için bkz: [bir etki alanına özgü dil çözüm şablonu seçme](../modeling/choosing-a-domain-specific-language-solution-template.md).  
  
 **Ne, etki alanına özgü dil adı istiyorsunuz?**  
 Varsayılan olarak çözüm adı. Kod bu değerinden oluşturulur. Bir C# sınıf adı olarak geçerli olmalıdır.  
  
### <a name="file-extension-page"></a>Dosya uzantısı sayfası  
 **Hangi uzantısı model kullanım dosyalar?**  
 Yeni bir dosya uzantısı yazın.  
  
 Bu dosya uzantısı zaten bu bilgisayarı kullanmak için şu şekilde kaydedilmemiş olduğunu doğrulayın:  
  
 Kısmına bakın **diğer araçları ve uygulamaları kayıtlı bu uzantısını işlemek için**. İletisini görürseniz, **uygulamaları ya da Visual Studio Düzenleyicileri Bu uzantıyı kullanmak**, bu dosya uzantısı kullanabilirsiniz.  
  
 Araçlar ya da paketlerin listesini görürseniz, aşağıdakilerden birini yapmanız gerekir:  
  
-   Farklı bir dosya uzantısı yazın.  
  
     \-veya -  
  
-   Sıfırlama [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] deneysel örneği. Bu önceden hazırladığınız DSL'ler tümünün kaldırır. Üzerinde **Başlat** menüsünde tıklatın **tüm programlar**, **Microsoft Visual Studio 2010 SDK**, **Araçları**ve ardından **Sıfırla Microsoft Visual Studio 2010 deneysel örneği**. Yeniden kullanmak istediğiniz diğer DSL'ler yeniden oluşturabilirsiniz.  
  
     \-veya -  
  
-   Varsa bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bu dosya uzantısı kullanır uzantısı tam olarak yüklü olduğu, bilgisayarınızda, bunu kaldırın. Üzerinde **Araçları** menüsünde tıklatın **Uzantı Yöneticisi**.  
  
### <a name="product-settings-page"></a>Ürün Ayarları sayfası  
 **Yeni etki alanına özgü dil ait ürün adı nedir?**  
 Varsayılan olarak DSL adı.  
  
 Bu değer, Windows Gezgini (veya dosya Gezgini'ni) Bu dosya uzantısına sahip dosyalar açıklamak için kullanılır.  
  
 **Ürün ait şirket adı nedir?**  
 Şirketinizin adı.  
  
 Bu değer DSL paketinizi AssemblyInfo özelliklerine eklenmiştir.  
  
 **Bu çözümdeki projeler için kök ad alanı nedir?**  
 Bu, şirketinizin oluşan bir ad ve ürün adları için varsayılan olarak.  
  
### <a name="signing-page"></a>İmzalama sayfası  
 **Güçlü ad anahtar dosyası oluştur**  
 DSL derlemenizi imzalamak için yeni bir anahtar oluşturmak için varsayılan seçenektir.  
  
 **Varolan bir güçlü ad anahtarı kullanma**  
 Başka bir derleme, DSL tümleştirmek istiyorsanız bu seçeneği kullanın.  
  
 Güçlü adlandırma hakkında daha fazla bilgi için bkz: [bkz](http://go.microsoft.com/fwlink/?LinkId=186073).  

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Etki Alanına Özgü bir Dili Tanımlama](../modeling/how-to-define-a-domain-specific-language.md)  
[Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
