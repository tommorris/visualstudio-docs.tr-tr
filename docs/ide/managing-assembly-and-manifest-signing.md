---
title: Derleme ve bildirim imzalamayı yönetme | Microsoft Docs
ms.custom: ''
ms.date: 02/17/2017
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- manifests [Visual Studio]
- signing manifests [Visual Studio]
- application manifests [Visual Studio]
- assemblies [Visual Studio], signing
ms.assetid: 6c1ef36b-25f7-4ad0-b29a-51801b7a5420
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2104ea0a86b351d0300bb7327c338dfcb0cd1818
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="managing-assembly-and-manifest-signing"></a>Derleme ve Bildirim İmzalamayı Yönetme
Tanımlayıcı ad imzası bir yazılım bileşeni genel olarak benzersiz bir kimliği verir. Tanımlayıcı adlar derleme başka birisi tarafından gibi görünerek edilemez olduğunu garanti ve bileşen bağımlılıklar ve yapılandırma deyimleri doğru bileşeni ve bileşen sürümü harita sağlamak için kullanılır.  
  
 Güçlü bir ad, bir ortak anahtar belirteci ve dijital imza derlemenin kimliğini (düz metin ad, sürüm numarasını ve kültür bilgilerini) oluşur.  
  
 Visual Basic ve C# projelerine imzalama derlemeler hakkında daha fazla bilgi için bkz: [bkz](http://msdn.microsoft.com/Library/ffbf6d9e-4a88-4a8a-9645-4ce0ee1ee5f9).  
  
 Visual C++ projelerinde imzalama derlemeler hakkında daha fazla bilgi için bkz: [tanımlayıcı ad derlemeleri (derleme imzalama) (C + +/ CLI)](/cpp/dotnet/strong-name-assemblies-assembly-signing-cpp-cli).  

> [!NOTE]
>  Tanımlayıcı ad imzası ters mühendislik karşı derlemenin korumaz.  Ters mühendislik karşı korumak için bkz: [Dotfuscator Community Edition (CE)](dotfuscator/index.md).
  
## <a name="asset-types-and-signing"></a>Varlık türleri ve imzalama  
 .NET derleme ve uygulama bildirimlerini imzalayabilirsiniz. Bunlar aşağıdakileri içerir:  
  
-   yürütülebilir dosyalar (.exe)  
  
-   uygulama bildirimleri (. exe.manifest)  
  
-   dağıtım bildirimleri (.application)  
  
-   Paylaşılan bileşen derlemeleri (.dll)  
  
Aşağıdaki varlık türlerini oturum açmanız gerekir:  
  
1.  Derlemeleri genel derleme önbelleği (GAC) dağıtmak istiyorsanız.  
  
2.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Uygulama ve dağıtım bildirimlerini. Visual Studio, varsayılan olarak bu uygulamalar için imzalama sağlar.  
  
3.  COM birlikte çalışabilirlik için kullanılan birincil birlikte çalışma derlemeleri. Birincil birlikte çalışma derlemesi COM tür kitaplığından oluştururken, TLBIMP yardımcı programı güçlü adlandırma zorlar.  
  
Genel yürütülebilir dosyalar oturumunuzu. Kesin adlandırılmış bir bileşeni uygulama ile dağıtılan kesin adlandırılmış bir bileşen başvuramaz. Visual Studio uygulama yürütülebilir dosyalar oturum değil, ancak bunun yerine zayıf adlı yürütülebilir dosyaya işaret uygulama bildirimi imzalanır. Genellikle, imzalama daha bağımlılıkları yönetmek zorlaştırabilir olduğundan, uygulamanız için özel bileşenleri imzalama kaçınmalısınız.  
  
## <a name="how-to-sign-an-assembly-in-visual-studio"></a>Visual Studio'da bir derleme imzalama  
 Bir uygulama veya bileşenin kullanarak oturum **imzalama** proje penceresinin sekmesinde (proje düğümüne sağ tıklayın **Çözüm Gezgini** seçip **özellikleri**, veya türü **proje özellikleri** içinde **hızlı başlatma** penceresinde veya içinde alt + ENTER tuşuna basın **Çözüm Gezgini** penceresi). Seçin **imzalama** sekmesini ve ardından **derlemeyi imzalamak** onay kutusu.  
  
 Bir anahtar dosyası belirtin. Yeni bir anahtar dosyası oluşturmayı seçerseniz, yeni anahtar dosyaları .pfx biçiminde her zaman oluşturulduğunu unutmayın. Yeni dosya için bir ad ve parola gerekir.  
  
> [!WARNING]
>  Her zaman başka birinin kullanmasını önlemek için bir parola ile anahtar dosyanızı korumanız gerekir. Ayrıca sağlayıcılar veya sertifika depolarını kullanarak anahtarlarınızı güvenliğini sağlayabilirsiniz.  
  
 Ayrıca, önceden oluşturduğunuz bir anahtarı işaret edebilir. Anahtarları oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir genel-özel anahtar çifti oluşturma](/dotnet/framework/app-domains/how-to-create-a-public-private-key-pair).  
  
 Yalnızca bir ortak anahtar erişimi varsa, anahtar atama erteleme imzalamayı geciktirme kullanabilirsiniz. Seçerek imzalamayı geciktirme etkinleştirmek **gecikme yalnızca oturum** onay kutusu. Gecikmeli imzalanmış bir proje çalışmaz ve hata ayıklaması yapılamıyor. Ancak, kullanarak doğrulama geliştirme sırasında atlayabilirsiniz [Sn.exe (tanımlayıcı ad aracı)](/dotnet/framework/tools/sn-exe-strong-name-tool) ile `-Vr` seçeneği.  
  
 Bildirimleri imzalama hakkında daha fazla bilgi için bkz: [nasıl yapılır: oturum uygulama ve dağıtım bildirimlerini](../ide/how-to-sign-application-and-deployment-manifests.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tanımlayıcı adlı derlemeler](/dotnet/framework/app-domains/strong-named-assemblies)   
 [Tanımlayıcı Ad Derlemeleri (Derleme İmzalama) (C++/CLI)](/cpp/dotnet/strong-name-assemblies-assembly-signing-cpp-cli)