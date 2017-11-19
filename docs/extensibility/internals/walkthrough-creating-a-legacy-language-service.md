---
title: "İzlenecek yol: bir eski dil hizmeti oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: language services [managed package framework], creating
ms.assetid: 6a5dd2c2-261b-4efd-a3f4-8fb90b73dc82
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 256a609dad857097731e4914a11623fe62ad7664
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-a-legacy-language-service"></a>İzlenecek yol: bir eski dil hizmeti oluşturma
Bir dil hizmetinde uygulamak için yönetilen paket framework (MPF) dil sınıfları kullanmaya [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] basittir. Dil hizmeti, dil hizmeti ve dilinizi için ayrıştırıcı barındırmak için bir VSPackage gerekir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda izlemek için Visual Studio SDK'yı yüklemeniz gerekir. Daha fazla bilgi için bkz: [Visual Studio SDK](../../extensibility/visual-studio-sdk.md).  
  
## <a name="locations-for-the-visual-studio-package-project-template"></a>Visual Studio Paketi proje şablonu için konumları  
 Visual Studio Paketi proje şablonu üç farklı bir şablon konumlarda bulunabilir **yeni proje** iletişim kutusunda:  
  
1.  Visual Basic genişletilebilirliği altında. Visual Basic projesinin varsayılan dildir.  
  
2.  C# genişletilebilirlik altında. Varsayılan proje C# dilidir.  
  
3.  Diğer proje türleri genişletilebilirlik altında. C++ projesinin varsayılan dildir.  
  
### <a name="create-a-vspackage"></a>Bir VSPackage oluşturma  
  
1.  Yeni bir VSPackage ile Visual Studio Paketi proje şablonu oluşturun.  
  
     Bir dil hizmeti için mevcut bir VSPackage ekliyorsanız, aşağıdaki adımları atlayın ve doğrudan "dil hizmeti Sınıf Oluştur" yordamına gidin.  
  
2.  MyLanguagePackage proje adı girin ve tıklayın **Tamam**.  
  
     İstediğiniz herhangi bir ad kullanabilirsiniz. Burada ayrıntılı Bu yordamlarda MyLanguagePackage adı olarak varsayılır.  
  
3.  Seçin [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] dil ve yeni bir anahtar dosyası oluşturmak için seçeneği olarak. 
              **İleri**'ye tıklayın.  
  
4.  Uygun şirket ve paketi bilgilerini girin. 
              **İleri**'ye tıklayın.  
  
5.  Seçin **menü komutu**. 
              **İleri**'ye tıklayın.  
  
     Kod parçacıkları desteklemek istiyorsanız değil, yalnızca Son'u tıklatın ve sonraki adıma yoksay.  
  
6.  Girin **Ekle parçacığı** olarak **komut adı** ve `cmdidInsertSnippet` için **komut kimliği**. **Son**'a tıklayın.  
  
     **Komut adı** ve **komut kimliği** istediğiniz olabilir, bunlar yalnızca örnektir.  
  
### <a name="create-the-language-service-class"></a>Dil hizmet sınıfı oluşturma  
  
1.  İçinde **Çözüm Gezgini**, MyLanguagePackage projeye sağ tıklayın, seçin **Ekle**, **başvuru**ve ardından **Yeni Başvuru Ekle** düğmesi.  
  
2.  İçinde **Başvuru Ekle** iletişim kutusunda **Microsoft.VisualStudio.Package.LanguageService** içinde **.NET** sekmesinde **Tamam**.  
  
     Bu dil paketi projesi için yalnızca bir kez gerçekleştirilmesi gerekir.  
  
3.  İçinde **Çözüm Gezgini**, VSPackage projeye sağ tıklayın ve seçin **Ekle**, **sınıfı**.  
  
4.  Emin olun **sınıfı** şablonları listesinden seçilir.  
  
5.  Girin **MyLanguageService.cs** tıklatın ve sınıf dosyası adını **Ekle**.  
  
     İstediğiniz herhangi bir ad kullanabilirsiniz. Bu yordamlar burada ayrıntılı varsayar `MyLanguageService` adı.  
  
6.  Aşağıdaki MyLanguageService.cs dosyasına ekleyin `using` deyimleri.  
  
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#1](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_1.cs)]
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#1](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_1.vb)]  
  
7.  Değiştirme `MyLanguageService` öğesinden türetilen sınıfı <xref:Microsoft.VisualStudio.Package.LanguageService> sınıfı:  
  
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#2](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_2.cs)]
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#2](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_2.vb)]  
  
8.  "LanguageService" ve klasörlerdeki imleç Konumlandır **Düzenle**, **IntelliSense** menüsünde, select **uygulama soyut sınıf**. Bu dil hizmet sınıfı uygulamak için en düşük gerekli yöntemleri ekler.  
  
9. Soyut yöntemler bölümünde açıklandığı gibi uygulamak [eski dil hizmeti uygulama](../../extensibility/internals/implementing-a-legacy-language-service2.md).  
  
### <a name="register-the-language-service"></a>Dil hizmet kaydı  
  
1.  MyLanguagePackagePackage.cs dosyasını açın ve aşağıdakileri ekleyin `using` deyimleri:  
  
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#3](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_3.vb)]
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#3](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_3.cs)]  
  
2.  Dil hizmet sınıfınızı açıklandığı şekilde kaydedin [eski dil hizmeti kaydetme](../../extensibility/internals/registering-a-legacy-language-service1.md). Bu ProvideXX öznitelikleri ve "Dil hizmeti Proffering" bölümleri içerir. Bu konuda TestLanguageService burada kullanır MyLanguageService kullanın.  
  
### <a name="the-parser-and-scanner"></a>Ayrıştırıcı ve tarayıcı  
  
1.  Ayrıştırıcı ve tarayıcı dilinizi için bölümünde açıklandığı gibi uygulamak [eski dil hizmeti Ayrıştırıcı ve tarayıcı](../../extensibility/internals/legacy-language-service-parser-and-scanner.md).  
  
     Ayrıştırıcı ve tarayıcı nasıl yapabileceğinize tamamen size kalmıştır ve bu konunun kapsamı dışındadır.  
  
## <a name="language-service-features"></a>Dil hizmet özellikleri  
 Her bir özelliğin dil hizmetinde uygulamak için genellikle uygun MPF dil hizmet sınıfından bir sınıf türetin, herhangi bir Özet yöntem gerektiği gibi uygulamak ve uygun yöntemleri geçersiz kılın. Desteklemek istediğiniz, oluşturma ve/veya öğesinden türetilen sınıfları özelliklerine bağlıdır. Bu özellikleri ayrıntılı olarak ele alınmıştır [eski dil hizmet özellikleri](../../extensibility/internals/legacy-language-service-features1.md). Aşağıdaki yordam, bir sınıf MPF sınıflarından türetme için genel yaklaşım kullanılır.  
  
#### <a name="deriving-from-an-mpf-class"></a>Bir MPF sınıfından türetme  
  
1.  İçinde **Çözüm Gezgini**, VSPackage projeye sağ tıklayın ve seçin **Ekle**, **sınıfı**.  
  
2.  Emin olun **sınıfı** şablonları listesinden seçilir.  
  
     Sınıf dosyası için uygun bir ad girin ve tıklayın **Ekle**.  
  
3.  Yeni sınıf dosyasında, aşağıdaki ekleyin `using` deyimleri.  
  
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#4](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_4.cs)]
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#4](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_4.vb)]  
  
4.  İstenen MPF sınıfından türetilen sınıfı değiştirin.  
  
5.  En az temel sınıfın Oluşturucusu aynı parametreleri alan bir sınıf oluşturucu ekleyin ve Oluşturucusu parametreleri temel sınıf oluşturucu açın.  
  
     Bir sınıf oluşturucusu gibi türetilen <xref:Microsoft.VisualStudio.Package.Source> sınıfı, şu şekilde görünebilir:  
  
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#5](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_5.cs)]
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#5](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_5.vb)]  
  
6.  Gelen **Düzenle**, **IntelliSense** menüsünde, select **uygulama soyut sınıf** temel sınıfı uygulanmalı herhangi bir Özet yöntem varsa.  
  
7.  Aksi takdirde, sınıf içinde şapka getirin ve geçersiz kılınacak yöntemi girin.  
  
     Örneğin, `public override` bu sınıfta geçersiz kılınmak tüm yöntemleri listesini görmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti uygulama](../../extensibility/internals/implementing-a-legacy-language-service1.md)