---
title: Uygulama kaynakları (.NET) yönetme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fe35a9a0e9b1e4b2e04e978f2b32cb38439b76cd
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="manage-application-resources-net"></a>Uygulama kaynakları (.NET) yönetme

Kaynak dosyaları, bir uygulamanın parçası olan ancak derlenmemiş, örnek simge dosyaları ya da ses dosyaları için dosyalarıdır. Bu dosyalar derleme işleminin bir parçası olmadığından, ikili dosyaları yeniden derlemenize gerek kalmadan değiştirebilirsiniz. Uygulamanızı yerelleştirme planlıyorsanız, tüm dizeler ve uygulamanızı yerelleştirme sırasında değiştirilmesi gereken diğer kaynaklar için kaynak dosyaları kullanmalısınız.

.NET masaüstü uygulamalarında kaynakları hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index).

## <a name="work-with-resources"></a>Kaynakları ile çalışma

Yönetilen kod projesi içinde proje Özellikler penceresini açın. Özellikler penceresini ya da açabilirsiniz:

- ' nde proje düğümüne sağ tıklayarak **Çözüm Gezgini** ve seçerek **özellikleri**
- "özellikleri proje" yazarak **hızlı başlatma** penceresi
- seçme **Alt**+**Enter** içinde **Çözüm Gezgini** penceresi

Seçin **kaynakları** sekmesi. Ekleyebileceğiniz bir *.resx* projenizi değil bir zaten içermelidir, Ekle ve kaynakları farklı türde silme ve mevcut kaynaklarına değiştirme dosyası.

## <a name="resources-in-other-project-types"></a>Kaynakları diğer proje türleri

Kaynakları farklı .NET projelerinde diğer proje türleri yönetilir. Kaynakları hakkında daha fazla bilgi için:

- Evrensel Windows Platformu (UWP) uygulamaları, bkz: [uygulama kaynakları ve kaynak yönetim sistemi](/windows/uwp/app-resources/)
- C++ projeleri bkz [kaynak dosyalarıyla çalışma](/cpp/windows/working-with-resource-files) ve [nasıl yapılır: kaynak oluşturma](/cpp/windows/how-to-create-a-resource)

## <a name="see-also"></a>Ayrıca bkz.

- [Masaüstü uygulamalarında (.NET Framework) kaynakları](/dotnet/framework/resources/index)
