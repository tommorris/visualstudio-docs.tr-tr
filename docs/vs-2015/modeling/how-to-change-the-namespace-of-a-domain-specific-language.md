---
title: 'Nasıl yapılır: bir etki alanına özgü dil Namespace Değiştir | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, namespace
ms.assetid: f20c47e5-230d-4f0e-812f-5c6edb86866c
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: bda1db0b3c20cdbeeb35f8ce0af6478a2a4f62c9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688439"
---
# <a name="how-to-change-the-namespace-of-a-domain-specific-language"></a>Nasıl yapılır: Etki Alanına Özgü bir Dilin Ad Alanını Değiştirme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: bir etki alanına özgü dil Namespace değiştirme](https://docs.microsoft.com/visualstudio/modeling/how-to-change-the-namespace-of-a-domain-specific-language).  
  
Etki alanına özgü bir dilin ad alanını değiştirebilirsiniz. Değişiklik yapmanız gereken **DSL Gezgini**, Dsl paket proje özelliklerinde ve derleme bilgileri.  
  
### <a name="to-change-the-namespace-of-a-domain-specific-language"></a>Etki alanına özgü bir dilin ad alanını değiştirmek için  
  
1.  İçinde **DSL Gezgini**, tıklayın **Dsl** düğümü.  
  
2.  İçinde **özellikleri** penceresinde değişiklik **Namespace** özelliği.  
  
3.  Çözüm kaydedin ve şablonlarını Dönüştür.  
  
4.  Üzerinde **proje** menüsünü tıklatın **Dsl özellikleri**.  
  
     Projeniz için Özellikler görünür.  
  
5.  Tıklayın **uygulama** sekmesi.  
  
6.  Değişiklik **varsayılan ad alanı** özelliğini yeni ad alanı adı.  
  
7.  Derlemenin adı değiştirmek istiyorsanız, değişiklik **bütünleştirilmiş kodun ad özelliği.**  
  
8.  Derleme adı değişmişse DslPackage\Package.tt açın ve bu satırı güncelleştirin:  
  
     `string dslAssembly = "YourDSLassembly.Dsl.dll";`  
  
9. Herhangi bir özel kod yazdığınız, kod dosyalarında ad alanını ve sınıf başvuruları değiştirdiğinizden emin olun.  
  
10. Visual Studio deneysel örneği sıfırlayın.  
  
    1.  Silme **\Users\\ ***{adınız}*** \AppData\Local\Microsoft\VisualStudio\\\*üs**  
  
    2.  Windows üzerinde **Başlat** menüsünde seçin **tüm programlar**, **Microsoft Visual Studio 2010 SDK**, **Araçları**, **Sıfırla Deneysel örneği**.  
  
11. Üzerinde **derleme** menüsünde seçin **çözümü yeniden derle**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



