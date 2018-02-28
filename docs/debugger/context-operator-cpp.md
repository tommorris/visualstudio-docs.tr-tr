---
title: "Context işleci (C++) hata ayıklayıcısında | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.operators
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- expressions [C++], native debugger
- evaluation
- format specifiers, expressions
- context operator, in expressions
- debugging [C++], expressions
- native expression evaluator
ms.assetid: 73cc9afe-f4a4-474e-bb89-5a33fb5e570c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1cae22698a0200dc0971f45dbcfd7b28005f8f0c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="context-operator-in-the-visual-studio-debugger-c"></a>Context işleci Visual Studio hata ayıklayıcısında (C++)
C++'ta context işleci bir kesme noktası konumu, değişken adı veya ifade nitelemek için kullanabilirsiniz. Context işleci, aksi takdirde yerel adıyla gizli bir dış kapsamdan bir ad belirtmek için kullanışlıdır.  
  
##  <a name="BKMK_Using_context_operators_to_specify_a_symbol"></a>Sözdizimi  
 Bağlam belirtmenin iki yolu vardır:  
  
1.  {,, [*Modülü*]} *ifade*  
  
     Küme ayraçları iki virgül ve modül içermelidir (yürütülebilir veya DLL) adını veya tam yolu.  
  
     Örneğin, bir kesme noktasında ayarlamak için `SomeFunction` EXAMPLE.dll işlevinin:  
  
    ```C++  
    {,,EXAMPLE.dll}SomeFunction  
    ```  
  
2.  *Modül*! *ifade*  
  
    ```C++  
    EXAMPLE.dll!SomeFunction  
    ```  
  
-   *Modül* bir modül adıdır. Aynı ada sahip modülleri arasında belirsizliğini ortadan kaldırmak için tam bir yol kullanabilirsiniz.  
  
     Varsa *Modülü* yolunu içeren bir virgülle, katıştırılmış bir boşluk veya bir küme parantezi, bağlam ayrıştırıcı dize düzgün tanıyabilmesi, yolu tırnak işaretleri kullanmanız gerekir. Çift tırnak işaretleri kullanmalısınız tek tırnak işareti bir Windows dosya adının bir parçası olarak kabul edilir. Örneğin,  
  
    ```C++  
    {,,"a long, long, library name.dll"} g_Var  
    ```  
  
-   *ifade* işlev adı, değişken adı veya işaretçi adresi gibi geçerli bir hedef çözümler tüm geçerli C++ ifadesidir *Modülü*.  
  
 İfade değerlendirici bir ifadede bir simge karşılaştığında simgenin aşağıdaki sırayla arar:  
  
1.  Geçerli bir blok, ayraçlar içinde ve dışa kapsayan blok ile devam etmeden deyimleri dizi başlayarak dışa doğru sözcük kapsamı. Geçerli blok yönerge işaretçisi adresi geçerli konumunu içeren kodudur.  
  
2.  İşlev kapsamı. Geçerli işlev.  
  
3.  Sınıf kapsamı, geçerli konumu C++ üye işlevi içinde ise. Sınıf kapsamı tüm temel sınıflar içerir. İfade değerlendirici normal hakimiyeti kurallarını kullanır.  
  
4.  Geçerli modülündeki genel simgeler.  
  
5.  Genel simgeler geçerli programı.