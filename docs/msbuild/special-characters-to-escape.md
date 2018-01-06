---
title: "Kaçış için özel karakterler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- special characters to escape
- msbuild, special characters to escape
ms.assetid: 5b5172c3-41e4-4f38-a16f-2aeac831a5fc
caps.latest.revision: "8"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2fde39272a9e9ededafd28a26a13f8c3adb9aaaf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="special-characters-to-escape"></a>Kaçış İçin Özel Karakterler
Bunlar, kullanıldıkları bağlamda özel bir anlamı yalnızca varsa, özel karakterler kaçış uygulanmalıdır. Örneğin, yıldız işareti (*) bir özel karakter yalnızca bir öğe tanımı "Ekle" ve "Dışarıda" özniteliklerini veya çağrı <xref:Microsoft.Build.Tasks.CreateItem>. Diğer durumlarda, yıldız işareti değişmez değer bir yıldız işareti olarak kabul edilir. Proje dosyalarında her yerde yıldızlar kaçış gerekmez, ancak bunu yaptığınızda bu nedenle hiçbir zarar yapar.  
  
 Gösterimi % kullanın*xx* özel karakter yerine burada *xx* ASCII karakter onaltılı değerini temsil eder. Örneğin, bir harf karakter olarak yıldız işareti (*) kullanmak için değeri kullanın `%2A`.  
  
 Kaçış için özel karakterler tam listesi aşağıdadır:  
  
|Karakter|Açıklama|  
|---------------|-----------------|  
|%|Meta veri başvurmak için kullanılan yüzde işareti.|  
|$|Dolar işareti, Özellikler başvurmak için kullanılan.|  
|@|Öğe listelerini başvurmak için kullanılan oturum sırasında.|  
|(|Açık parantezleri, listelerinde kullanılır.|  
|)|Kapatma parantezi, listelerinde kullanılır.|  
|`|Kesme işareti (veya değer çizgisi), koşulları ve diğer ifadeleri kullanılır.|  
|;|Noktalı virgül, liste ayırıcısı.|  
|?|Soru işareti, bir öğenin ekleme/çıkarma bölümünde dosya spec açıklanırken bir joker karakter.|  
|*|Yıldız işareti, bir öğenin ekleme/çıkarma bölümünde dosya spec açıklanırken bir joker karakter.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: MSBuild özel karakterleri kaçış](../msbuild/how-to-escape-special-characters-in-msbuild.md)   
 [MSBuild Başvurusu](../msbuild/msbuild-reference.md)