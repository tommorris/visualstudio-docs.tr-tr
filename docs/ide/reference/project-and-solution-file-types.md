---
title: Proje ve Çözüm Dosya Türleri
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- File Properties.CopyToOutputDirectory
- File Properties.CustomToolNamespace
- File Properties.FileName
- File Properties.FullPath
- File Properties.BuildAction
- File Properties.CustomTool
- FileProperties
helpviewer_keywords:
- .sln files
- .suo files
- file types [Visual Studio]
- file extensions [Visual Studio]
- solution files [Visual Studio]
- sln files
- suo files
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b3786d6f38e4f87aa05a51b0a6112613bda65e56
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31947605"
---
# <a name="project-and-solution-file-types"></a>Proje ve çözüm dosya türleri

Visual Studio, çok sayıda dosya türlerini destekler. Belirli bir yüklemede, hangi dosya türlerinin desteklendiği yüklü bileşenlerin belirler. Bu konu, bazı tipik yüklemelerde desteklenen çözüm ve proje dosya türleri listelenmektedir.

## <a name="solution-files-sln-and-suo"></a>Çözüm dosyalarını (.sln ve .suo)

Visual Studio iki dosya türleri (.sln ve .suo) çözümler için ayarları depolamak için kullanır. Topluca çözüm dosyalarını bilinen bu dosyalar, Çözüm Gezgini dosyalarınızı yönetmek için bir grafik arabirim görüntülemek için gereken bilgileri sağlar.

|Uzantısı|Ad|Açıklama|
|---------------|----------|-----------------|
|.sln|Visual Studio çözümü|Proje, proje öğeleri ve çözüm öğeleri çözüme düzenler.|
|.suo|Çözüm kullanıcı seçenekleri|Visual Studio için kesme noktaları gibi yapmış olduğunuz kullanıcı düzeyinde özelleştirmeleri takip eder.|

## <a name="project-files"></a>Proje dosyaları

Projeleri birçok farklı dosya türleri içerebilir. Örneğin, C# kod dosyaları sahip bir **.cs** uzantısı ve C++ dosyaları sahip bir **.cpp** uzantısı. İçinde depolanan kaynaklar **.resx** dosyaları ve XAML'de **.xaml** dosyaları. [App.config](../../ide/managing-application-settings-dotnet.md) dosyaları içeren uygulama kodunda dahil edilmemesi gereken uygulama bilgilerini&mdash;örneğin bağlantı dizeleri.

C++ projelerine dosya türleri hakkında daha fazla bilgi için bkz: [Visual C++ projeleri için oluşturulan dosya türleri](/cpp/ide/file-types-created-for-visual-cpp-projects).

## <a name="see-also"></a>Ayrıca bkz.

- [Çözümler ve projeler](../../ide/solutions-and-projects-in-visual-studio.md)