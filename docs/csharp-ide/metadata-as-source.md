---
title: Kaynak olarak meta veriler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- Go To Definition command
- Code Definition window, viewing metadata as source
- metadata as source [C#]
ms.assetid: 4945a07f-b3be-4f05-a587-fc29058aa8fa
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 118d19a1be813b0488503be86a316ccc82bd7b37
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="metadata-as-source"></a>Kaynak olarak Meta Veriler
Kaynak olarak meta veriler, C# kaynak kodu salt okunur bir arabellek olarak görünür meta verileri görüntülemenize olanak tanır. Bu bildirimler türleri ve üyeleri (uygulamaları olmadan), bir görünümünü sağlar. Meta veri kaynağı olarak çalıştırarak görüntüleyebileceğiniz **Tanıma Git** komutunu türleri veya üyeleri olan kaynak kodu proje ya da çözüm kullanılabilir değil.  
  
> [!NOTE]
>  Çalıştırmak çalıştığınızda **Tanıma Git** komut türleri veya dahili olarak işaretlenmiş üyeleri için tümleşik geliştirme ortamı (IDE) görüntülemiyor bunların meta verilerini bağımsız olarak mı yoksa kaynak olarak başvuran derleme arkadaş olup.  
  
 Her iki kod düzenleyicisinde kaynak olarak meta verilerini görüntüleyebilirsiniz veya **kod tanımı** penceresi.  
  
## <a name="viewing-metadata-as-source-in-the-code-editor"></a>Kod Düzenleyicisi'nde kaynak olarak meta verileri görüntüleme  
 Çalıştırdığınızda **Tanıma Git** komutu, kaynak kodu kullanılamıyorsa bir öğe için bu öğeye ait meta verileri, kaynağı olarak görüntülenen bir görünümünü içeren sekmeli belge Kod Düzenleyicisi'nde görünür. Türünün adını ve ardından **[from meta verileri]**, belgenin sekmesinde görünür.  
  
 Örneğin çalıştırırsanız **Tanıma Git** komutunu <xref:System.Console>, meta verileri <xref:System.Console> bildiriminden benzer C# kaynak kodu, ancak bir uygulama olmadan Kod Düzenleyicisi'nde görüntülenir.  
  
 ![Kaynak olarak meta veriler](../csharp-ide/media/metadatasource.png "MetadataSource")  
  
## <a name="viewing-metadata-as-source-in-the-code-definition-window"></a>Kod tanımı penceresi kaynak olarak meta veri görüntüleme  
 Zaman **kod tanımı** pencere etkin veya görünür, IDE otomatik olarak yürütür **Tanıma Git** ve içindeseçiliöğeleriçinKodDüzenleyicisi'ndeimleçaltındakiöğelerekomutu **Sınıf Görünümü** veya **Nesne Tarayıcısı**. Kaynak kodu bu öğe için kullanılabilir durumda değilse, IDE öğesi'nin meta veri kaynağı olarak görüntüler. **kod tanımı** penceresi.  
  
 Örneğin, imlecinizi sözcük içindeki yerleştirirseniz <xref:System.Console> Kod Düzenleyicisi'nde, meta verileri <xref:System.Console> kaynağı olarak görünür **kod tanımı** penceresi. Kaynak benzer <xref:System.Console> bildirimi, bir uygulama olmadan.  
  
 Görüntülenen öğeyi bildirimi görmek istediğinizde **kod tanımı** penceresinde, öğeyi sağ tıklatın ve **Tanıma Git**.