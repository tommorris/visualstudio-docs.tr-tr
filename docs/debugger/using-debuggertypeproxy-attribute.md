---
title: "DebuggerTypeProxy özniteliğini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- attributes [C#], debugger
- DebuggerTypeProxyAttribute class
- DebuggerTypeProxy attribute
ms.assetid: 943f3bb1-993e-4800-a47e-0af78b063014
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 36e80508ce0febc7678585faf6518bf6b838a289
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="using-debuggertypeproxy-attribute"></a>DebuggerTypeProxy Özniteliğini Kullanma
<xref:System.Diagnostics.DebuggerTypeProxyAttribute>bir proxy ya da bir türü ve türü yolu hata ayıklayıcı Windows'da görüntülenir değişiklikler için stand-in belirtir. Bir proxy sahip bir değişken görüntülediğinizde, proxy özgün türü için anlamına gelir **görüntülemek**. Hata ayıklayıcı değişken penceresinde yalnızca Genel üyeler proxy türü görüntüler. Özel üyelerin görüntülenmez.  
  
 Bu öznitelik için uygulanabilir:  
  
-   Yapılar  
  
-   Sınıflar  
  
-   Derlemeler  
  
 Bir tür proxy sınıfı proxy yerini alacak türünde bir bağımsız değişken bir oluşturucuya sahip olmalıdır. Hedef türünde bir değişken görüntülemek gereken her zaman hata ayıklayıcı türü proxy sınıfının yeni bir örneğini oluşturur. Bu performans etkileri olabilir. Sonuç olarak, her türlü Oluşturucusu daha fazla iş kesinlikle gerekli daha yapmamanız gerekir.  
  
 Kullanıcı tıklayarak türü genişletilmiş sürece performans cezaları en aza indirmek için ifade değerlendiricisi görüntü proxy türü özniteliklerinde inceleyin değil + simgesi hata ayıklayıcı penceresinde veya kullanımını <xref:System.Diagnostics.DebuggerBrowsableAttribute>. Bu nedenle, özniteliklerine görüntü türü kendisi girmeniz gerekir. Öznitelikleri olabilir ve görüntü türü gövdesinde kullanılmalıdır.  
  
 Özel bir iç içe geçmiş sınıf sınıfı içinde olacak şekilde türü proxy'si için iyi bir fikir değil, öznitelik hedefleri. Bu, iç üyelere kolayca erişmek sağlar.  
  
 Varsa <xref:System.Diagnostics.DebuggerTypeProxyAttribute> derleme düzeyinde kullanılan `Target` parametresi, proxy değiştirilecek türünü belirtir.  
  
 Bu öznitelik ile birlikte kullanma örneği için <xref:System.Diagnostics.DebuggerDisplayAttribute> ve <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, bkz:[DebuggerDisplay özniteliğini kullanma](../debugger/using-the-debuggerdisplay-attribute.md).  
  
## <a name="using-generics-with-debuggertypeproxy"></a>Genel türler DebuggerTypeProxy ile kullanma  
 Genel türler için destek sınırlıdır. C# ' ta, `DebuggerTypeProxy` yalnızca açık türlerini destekler. Unconstructed bir türü olarak da adlandırılan bir açık tür parametreleri için bağımsız değişkenlerle oluşturulmadı genel bir tür türüdür. Oluşturulan türler olarak da bilinir kapalı türleri desteklenmez.  
  
 Açık bir tür için sözdizimi şu şekildedir:  
  
 `Namespace.TypeName<,>`  
  
 Bir hedef olarak genel bir tür kullanıyorsanız `DebuggerTypeProxy`, şu sözdizimini kullanmanız gerekir. `DebuggerTypeProxy` Mekanizması sizin için tür parametreleri oluşturur.  
  
 C# açık ve kapalı türleri hakkında daha fazla bilgi için bkz: [C# dil belirtimi](/dotnet/csharp/language-reference/language-specification), Bölüm 20.5.2 açık ve kapalı türleri.  
  
 Visual Basic'te aynı şeyi yapamayacağı şekilde Visual Basic açık tür sözdizimine sahip değil. Bunun yerine, açık tür adı bir dize gösterimini kullanmanız gerekir.  
  
 `"Namespace.TypeName'2"`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DebuggerDisplay özniteliğini kullanma](../debugger/using-the-debuggerdisplay-attribute.md)   
 [.Managed nesnelerin özel görünümlerini oluşturma](../debugger/create-custom-views-of-dot-managed-objects.md)   
 [Hata Ayıklayıcı Görüntü Öznitelikleriyle Hata Ayıklamayı Geliştirme](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)