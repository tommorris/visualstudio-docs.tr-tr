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
- editors [Visual Studio], Resource Designer
- Resource Designer
- resources [Visual Studio], managing
- Resources page in Project Designer
- resources types, Resource Designer
- application resources [Visual Studio]
- Project Designer, Resources page
ms.assetid: f2582734-8ada-4baa-8a7c-e2ef943ddf7e
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b599a919911fcc5d2833cfe69b75f7b32cced858
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="managing-application-resources-net"></a>Uygulama Kaynaklarını Yönetme (.NET)
Kaynak dosyaları, bir uygulamanın parçası olan ancak derlenmemiş, örnek simge dosyaları ya da ses dosyaları için dosyalarıdır. Bu dosyalar derleme işleminin bir parçası olmadığından, ikili dosyaları yeniden derlemenize gerek kalmadan değiştirebilirsiniz. Uygulamanızı yerelleştirme planlıyorsanız, tüm dizeler ve uygulamanızı yerelleştirme sırasında değiştirilmesi gereken diğer kaynaklar için kaynak dosyaları kullanmalısınız.  
  
.NET masaüstü uygulamalarında kaynakları hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index). C++ masaüstü uygulamalarında kaynakları hakkında daha fazla bilgi için bkz: [kaynak dosyalarıyla çalışma](/cpp/windows/working-with-resource-files).  
  
UWP uygulamalar Masaüstü uygulamalarından farklı kaynak modeli kullanır. Windows 8.x uygulamalarında kaynakları hakkında daha fazla bilgi için bkz: [uygulama kaynakları (HTML) tanımlama](https://msdn.microsoft.com/en-us/library/windows/apps/hh465228.aspx).  
  
## <a name="working-with-resources"></a>Kaynakları ile çalışma  
Yönetilen kod projesi içinde proje Özellikler penceresini açın. Özellikler penceresini ya da açabilirsiniz:

- ' nde proje düğümüne sağ tıklayarak **Çözüm Gezgini** ve seçerek **özellikleri**
- yazmaya **proje özellikleri** içinde **hızlı başlatma** penceresi
- seçme **Alt + Enter** içinde **Çözüm Gezgini** penceresi

Seçin **kaynakları** sekmesi. Projenizi değil bir zaten içermelidir, Ekle ve kaynakları farklı türde silerseniz, ve var olan kaynakların değiştirmek .resx dosyası ekleyebilirsiniz.  
  
C++ projelerine kaynaklarla çalışmak nasıl öğrenmek için bkz: [nasıl yapılır: kaynak oluşturma](/cpp/windows/how-to-create-a-resource).