---
title: "Otomasyon modeline genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], about automation
- extensibility
ms.assetid: 12b6d6db-0d22-4aaa-aa7d-1365f759b7b0
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6d4fda81b18824560276c1398583b2674bf200ab
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="automation-model-overview"></a>Otomasyon modeline genel bakış
Otomasyon modeli karşı bir Visual Studio eklentisi veya uzantı yazabilirsiniz nesneler kümesinden oluşur. Bir eklenti, Visual Studio ortamı yönetmek ve ortak görevleri otomatik hale getirmek bir uygulamadır. Visual Studio uzantısı özel Visual Studio bileşenlerini oluşturmak veya metin düzenleyici gibi standart bileşenlerin işlevselliğini ekleyin.  
  
## <a name="objects-in-the-automation-model"></a>Otomasyon modeldeki nesneleri  
 Otomasyon modeli ilgili ortak ortam ana modelleri kontrol nesneler kümesinden oluşur. Otomasyon modeli oluşturma nesne kapsamlı kümesini gösteren diyagram verilmiştir.  
  
 ![Visual Studio Otomasyon nesnesi grafiği](../../extensibility/internals/media/vsvisualstudioautomationobjectchart.gif "vsVisualStudioAutomationObjectChart")  
Visual Studio Otomasyon nesneleri  
  
 Daha fazla bilgi için bkz: [Visual Studio ortamı genişletme](http://msdn.microsoft.com/Library/4173a963-7ac7-4966-9bb7-e28a9d9f6792).  
  
 Ortam bir model için farklı işlevsel alanlara sağlar. Örneğin, kodda bulabileceğiniz çeşitli öğeleri için kod modeli yoktur. Çeşitli belge öğeleri için bir belge modeli yoktur. Bir, Proje alanı VSPackage sağlayıcılarına belirli ilgi alanıdır. Otomasyon modeline kadar aynı şekilde katkıda bulunmak için yeni proje türleri büyük olasılıkla isteyeceksiniz [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] ve [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] otomasyon modeli katkıda bulunun. İşlem kısmında özetlenen [sağlayarak Otomasyon VSPackages için](../../extensibility/internals/providing-automation-for-vspackages.md).  
  
 Yerler burada ortamının otomasyon modeli genişletme düşünebilirsiniz:  
  
-   Project  
  
-   Belge  
  
-   Kod  
  
-   Derleme  
  
 Otomasyon hakkında daha fazla bilgi için bkz: [otomasyon ve genişletilebilirlik Visual Studio için](http://msdn.microsoft.com/Library/f71a2253-3e68-4e5e-9a18-edbba816caf6). Bu belge ve belgeler, otomasyon, VSPackage için nasıl sağladığını ilgili kararlar almanıza yardımcı olmak için bağlantılar sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir eklenti oluşturun](http://msdn.microsoft.com/Library/50be56d2-e3a5-4cd2-8569-2a0666b268ce)