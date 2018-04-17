---
title: Visual Studio'da projeye bir app.config dosyası ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 22b9ed31621074e27cfa2d51502e44d508d6b424
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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

[Uygulama ayarları (.NET) yönetme](../ide/managing-application-settings-dotnet.md)  
[Yapılandırma dosyası şeması (.NET Framework)](/dotnet/framework/configure-apps/file-schema/index)  
[Uygulamaları (.NET Framework) yapılandırma](/dotnet/framework/configure-apps/index)