---
title: Visual Studio'da projeye bir app.config dosyası ekleme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
dev_langs:
- CSharp
helpviewer_keywords:
- app.config files, adding to C# projects
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: b2182b0175d57d7283e63bdf408249fa7566da00
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31941980"
---
# <a name="how-to-add-an-application-configuration-file-to-a-c-project"></a>Nasıl yapılır: bir C# projesine uygulama yapılandırma dosyası ekleme

Bir uygulama yapılandırma dosyasına ekleyerek (*app.config* dosyası) bir C# projesi, ortak dil çalışma zamanı'nın bulur ve derleme dosyalarını yükler nasıl özelleştirebilirsiniz. Uygulama yapılandırma dosyaları hakkında daha fazla bilgi için bkz: [nasıl çalışma zamanı derlemeleri (.NET Framework) bulur](/dotnet/framework/deployment/how-the-runtime-locates-assemblies).

> [!NOTE]
> Verme UWP uygulamaları içeren bir *app.config* dosya.

Projenizi yapılandırdığınızda, geliştirme ortamı otomatik olarak kopyalar, *app.config* dosya, dosya adı yürütülebilir dosyanın eşleşecek şekilde kopyasının değiştirir ve ardından Kopyala taşır **bin** Dizin.

## <a name="to-add-an-application-configuration-file-to-a-c-project"></a>Bir C# projesine uygulama yapılandırma dosyası eklemek için

1. Menü çubuğunda seçin **proje** > **Yeni Öğe Ekle**.

     **Yeni Öğe Ekle** iletişim kutusu görüntülenir.

1. Genişletme **yüklü** > **Visual C# öğeleri**ve ardından **uygulama yapılandırma dosyası** şablonu.

1. İçinde **adı** metin kutusuna bir ad girin ve ardından **Ekle** düğmesi.

     Adlı bir dosya *app.config* projenize eklenir.

## <a name="see-also"></a>Ayrıca bkz.

- [Uygulama ayarları (.NET) yönetme](../ide/managing-application-settings-dotnet.md)
- [Yapılandırma dosyası şeması (.NET Framework)](/dotnet/framework/configure-apps/file-schema/index)
- [Uygulamaları (.NET Framework) yapılandırma](/dotnet/framework/configure-apps/index)