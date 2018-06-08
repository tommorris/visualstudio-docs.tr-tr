---
title: Derleme ve bildirim imzalamayı yönetme
ms.date: 02/17/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
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
ms.openlocfilehash: bef64670c3c2631e779fda0f48810ce502db72b1
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34844442"
---
# <a name="manage-assembly-and-manifest-signing"></a>Derleme ve bildirim imzalamayı yönetme

Tanımlayıcı ad imzası bir yazılım bileşeni genel olarak benzersiz bir kimliği verir. Tanımlayıcı adlar derleme başka birisi tarafından gibi görünerek edilemez olduğunu garanti ve bileşen bağımlılıklar ve yapılandırma deyimleri doğru bileşeni ve bileşen sürümü harita emin olmak için kullanılır.

Güçlü bir ad, bir ortak anahtar belirteci ve dijital imza derlemenin kimliğini (düz metin ad, sürüm numarasını ve kültür bilgilerini) oluşur.

Visual Basic ve C# projelerine imzalama derlemeler hakkında daha fazla bilgi için bkz: [tanımlayıcı adlı derlemeler oluşturma ve kullanma](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies).

Visual C++ projelerinde imzalama derlemeler hakkında daha fazla bilgi için bkz: [tanımlayıcı adlı derlemeler (C + +/ CLI)](/cpp/dotnet/strong-name-assemblies-assembly-signing-cpp-cli).

> [!NOTE]
> Tanımlayıcı ad imzası ters mühendislik karşı derlemenin korumaz. Ters mühendislik karşı korumak için bkz: [Dotfuscator Community Edition (CE)](dotfuscator/index.md).

## <a name="asset-types-and-signing"></a>Varlık türleri ve imzalama

.NET derleme ve uygulama bildirimlerini oturum açabilirsiniz:

- yürütülebilir dosyalar (*.exe*)

- uygulama bildirimleri (*. exe.manifest*)

- dağıtım bildirimleri (*.application*)

- Bileşen derlemeleri paylaşılan (*.dll*)

Aşağıdaki varlık türlerini imzalayın:

1. Derlemeleri genel derleme önbelleği (GAC) dağıtmak istiyorsanız.

2. ClickOnce Uygulama ve dağıtım bildirimlerini. Visual Studio, varsayılan olarak bu uygulamalar için imzalama sağlar.

3. COM birlikte çalışabilirlik için kullanılan birincil birlikte çalışma derlemeleri. Birincil birlikte çalışma derlemesi COM tür kitaplığından oluştururken, TLBIMP yardımcı programı güçlü adlandırma zorlar.

Genel olarak, yürütülebilir dosyalar oturumunuzu. Kesin adlandırılmış bir bileşeni uygulama ile dağıtılan kesin adlandırılmış bir bileşen başvuramaz. Visual Studio uygulama yürütülebilir dosyalar oturum değil, ancak bunun yerine zayıf adlı yürütülebilir dosyaya işaret uygulama bildirimi imzalanır. İmzalama daha bağımlılıkları yönetmek zorlaştırabilir olduğundan, uygulamanız için özel bileşenleri imzalama kaçının.

## <a name="how-to-sign-an-assembly-in-visual-studio"></a>Visual Studio'da bir derleme imzalama

Bir uygulama veya bileşenin kullanarak oturum **imzalama** proje penceresinin sekmesinde (proje düğümüne sağ tıklayın **Çözüm Gezgini** seçip **özellikleri**, veya türü **proje özellikleri** içinde **hızlı başlatma** penceresi veya tuşuna **Alt**+**Enter**içinde **Çözüm Gezgini** penceresi). Seçin **imzalama** sekmesini ve ardından **derlemeyi imzalamak** onay kutusu.

Bir anahtar dosyası belirtin. Yeni bir anahtar dosyası oluşturmayı seçerseniz, yeni anahtar dosyaları her zaman oluşturulan *.pfx* biçimi. Yeni dosya için bir ad ve parola gerekir.

> [!WARNING]
> Her zaman başka birinin kullanmasını önlemek için bir parola ile anahtar dosyanızı korumanız gerekir. Ayrıca sağlayıcılar veya sertifika depolarını kullanarak anahtarlarınızı güvenliğini sağlayabilirsiniz.

Ayrıca, önceden oluşturduğunuz bir anahtarı işaret edebilir. Anahtarları oluşturma hakkında daha fazla bilgi için bkz: [genel-özel anahtar çifti oluşturma](/dotnet/framework/app-domains/how-to-create-a-public-private-key-pair).

Bir ortak anahtar yalnızca erişiminiz varsa, anahtar atama erteleme Gecikmeli imzalama kullanabilirsiniz. Seçerek imzalamayı geciktirme etkinleştirmek **gecikme yalnızca oturum** onay kutusu. Gecikmeli imzalanmış bir proje çalışmaz ve hata ayıklaması yapılamıyor. Ancak, kullanarak doğrulama geliştirme sırasında atlayabilirsiniz [Sn.exe tanımlayıcı ad aracı](/dotnet/framework/tools/sn-exe-strong-name-tool) ile `-Vr` seçeneği.

Bildirimleri imzalama hakkında daha fazla bilgi için bkz: [nasıl yapılır: uygulama ve dağıtım bildirimlerini imzalama](../ide/how-to-sign-application-and-deployment-manifests.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Tanımlayıcı adlı derlemeler](/dotnet/framework/app-domains/strong-named-assemblies)
- [Tanımlayıcı adlı derlemeler (C + +/ CLI)](/cpp/dotnet/strong-name-assemblies-assembly-signing-cpp-cli)
