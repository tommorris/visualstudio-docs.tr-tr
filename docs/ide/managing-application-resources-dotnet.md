---
title: "Uygulama kaynaklarını (.NET) yönetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- msvse_resedit.dlg.SetCustomTool
- msvse_settingsdesigner.err.formatvalue
- msvse_resedit.err.nameblank
- msvse_resedit.err.duplicatename
helpviewer_keywords:
- Resource Designer
- resources [Visual Studio]
- Resources page in Project Designer
- application resources [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6645a1147b2ee5f5d5ba0b85a7f8999008f5ae19
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/14/2017
---
# <a name="managing-application-resources-net"></a>Uygulama kaynaklarını (.NET) yönetme

Kaynak dosyaları, bir uygulamanın parçası olan ancak derlenmemiş, örnek simge dosyaları ya da ses dosyaları için dosyalarıdır. Bu dosyalar derleme işleminin bir parçası olmadığından, ikili dosyaları yeniden derlemenize gerek kalmadan değiştirebilirsiniz. Uygulamanızı yerelleştirme planlıyorsanız, tüm dizeler ve uygulamanızı yerelleştirme sırasında değiştirilmesi gereken diğer kaynaklar için kaynak dosyaları kullanmalısınız.

.NET masaüstü uygulamalarında kaynakları hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index).

## <a name="working-with-resources"></a>Kaynakları ile çalışma

Yönetilen kod projesi içinde proje Özellikler penceresini açın. Özellikler penceresini ya da açabilirsiniz:

- ' nde proje düğümüne sağ tıklayarak **Çözüm Gezgini** ve seçerek **özellikleri**
- "özellikleri proje" yazarak **hızlı başlatma** penceresi
- seçme **Alt**+**Enter** içinde **Çözüm Gezgini** penceresi

Seçin **kaynakları** sekmesi. Projenizi değil bir zaten içermelidir, Ekle ve kaynakları farklı türde silerseniz, ve var olan kaynakların değiştirmek .resx dosyası ekleyebilirsiniz.

## <a name="resources-in-other-project-types"></a>Kaynakları diğer proje türleri

Kaynakları farklı .NET projelerinde diğer proje türleri yönetilir. Kaynakları hakkında daha fazla bilgi için:

- Evrensel Windows Platformu (UWP) uygulamaları, bkz: [uygulama kaynakları ve kaynak yönetim sistemi](/windows/uwp/app-resources/)
- Windows 8.x uygulamaları görmek [uygulama kaynakları (HTML) tanımlama](https://msdn.microsoft.com/en-us/library/windows/apps/hh465228.aspx)
- C++ projeleri bkz [kaynak dosyalarıyla çalışma](/cpp/windows/working-with-resource-files) ve [nasıl yapılır: kaynak oluşturma](/cpp/windows/how-to-create-a-resource)

## <a name="see-also"></a>Ayrıca bkz.

[Masaüstü uygulamalarında (.NET Framework) kaynakları](/dotnet/framework/resources/index)