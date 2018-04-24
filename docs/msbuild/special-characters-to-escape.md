---
title: Kaçış için özel karakterler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- special characters to escape
- msbuild, special characters to escape
ms.assetid: 5b5172c3-41e4-4f38-a16f-2aeac831a5fc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a155d2d85f0b6208b98587f6907c8dadfd92d737
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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