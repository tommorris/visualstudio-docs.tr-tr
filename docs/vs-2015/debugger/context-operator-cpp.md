---
title: Bağlam işleci (C++) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.operators
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- expressions [C++], native debugger
- evaluation
- format specifiers, expressions
- context operator, in expressions
- debugging [C++], expressions
- native expression evaluator
ms.assetid: 73cc9afe-f4a4-474e-bb89-5a33fb5e570c
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d8a3c033175b1ee7fcd0d7fcbaeae5d64a928289
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687602"
---
# <a name="context-operator-c"></a>Bağlam işleci (C++)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [bağlam işleci (C++)](https://docs.microsoft.com/visualstudio/debugger/context-operator-cpp).  
  
Bir kesme noktası konumu, değişken adı veya ifade nitelemek için C++'da şu içerik işlecini kullanabilirsiniz. Bağlam işleci, aksi takdirde yerel bir ad tarafından gizlenen bir dış kapsam adı belirtmek için kullanışlıdır.  
  
##  <a name="BKMK_Using_context_operators_to_specify_a_symbol"></a> Söz dizimi  
 Bağlam belirtmenin iki yolu vardır:  
  
1.  {, [*Modülü*]} *ifadesi*  
  
     Küme ayraçları iki virgül ve modül içermelidir (yürütülebilir veya DLL) adını veya tam yolu.  
  
     Örneğin, bir kesme noktasında ayarlanacak `SomeFunction` EXAMPLE.dll işlevi:  
  
    ```cpp  
    {,,EXAMPLE.dll}SomeFunction  
    ```  
  
2.  *Modül*! *ifade*  
  
    ```cpp  
    EXAMPLE.dll!SomeFunction  
    ```  
  
-   *Modül* bir modül adı. Aynı ada sahip modüller arasında ayırt etmek için bir tam yol kullanabilirsiniz.  
  
     Varsa *Modülü* yolu, virgül, katıştırılmış bir boşluk veya bir küme ayracı içerir, bağlam ayrıştırıcının dizesi düzgün tanıyabilmesi, yolu tırnak kullanmanız gerekir. Tek tırnak işaretleri çift tırnak işareti kullanmalısınız bir Windows dosya adının parçası olarak kabul edilir. Örneğin,  
  
    ```cpp  
    {,,"a long, long, library name.dll"} g_Var  
    ```  
  
-   *ifade* işlev adı, değişken adı veya işaretçi adresi gibi geçerli bir hedef çözümler herhangi geçerli bir C++ ifadesi *Modülü*.  
  
 İfade değerlendirici bir ifadede bir sembol karşılaştığında sembolünün şu sırayla arar:  
  
1.  Sözcük kapsamı geçerli blok küme ayraçları içine alındığına ve dışa doğru kapsayan bir blok ile devam bir deyimler serisini başlayarak dışa doğru. Geçerli blok yönerge işaretçisi adresi geçerli konumu içeren kodudur.  
  
2.  İşlev kapsamı. Geçerli işlev.  
  
3.  C++ üye işlevinin içerisinde geçerli konumu ise sınıf kapsamı. Sınıf kapsamı, tüm temel sınıflar içerir. İfade değerlendirici, normal baskınlık kurallarını kullanır.  
  
4.  Genel semboller geçerli modül içinde.  
  
5.  Ortak semboller geçerli programı.





