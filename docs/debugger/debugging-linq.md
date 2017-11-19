---
title: "LINQ'de hata ayıklama | Microsoft Docs"
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
- debugging, LINQ
- LINQ, viewing results in debugger
- LINQ, debugging
- LINQ, stepping
- LINQ, edit and continue
ms.assetid: dbae26cb-ac5f-4312-b474-b9f29714f4c6
caps.latest.revision: "25"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bfd356931e33e900d35094c4714d0c3f6fc93abe
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="debugging-linq"></a>LINQ'de Hata Ayıklama
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]hata ayıklama dilinin tümleşik destekler (LINQ) kodu, bazı kısıtlamalarla sorgu. Atlama, kesme noktalarını ayarlama ve hata ayıklayıcı pencerelerde sonuçları görüntüleme gibi LINQ ifadelerle en hata ayıklama özellikleri çalışmaz. Bu konuda LINQ hata ayıklama önemli sınırlamalar açıklanır.  
  
##  <a name="BKMK_ViewingLINQResults"></a>LINQ sonuçları görüntüleme  
 DataTips, Gözcü penceresi ve QuickWatch iletişim kutusunu kullanarak, bir LINQ ifadesi sonucu görüntüleyebilirsiniz. Bir kaynak penceresi kullandığınızda, kaynak penceresini sorguda işaretçisini duraklatabilirsiniz ve bir DataTip görüntülenir. LINQ değişkeni kopyalamak ve Gözcü penceresi veya QuickWatch iletişim kutusu yapıştırın.  
  
 LINQ, oluşturulduğunda veya bildirildi, ancak yalnızca sorgu kullanıldığında sorguda değerlendirilmez. Bu nedenle, sorgu ifadesine hesaplanmadan kadar bir değer yok. Sorgu oluşturma ve değerlendirme tam bir açıklaması için bkz: [LINQ sorgularını (C#) giriş](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries) veya [yazma bilgisayarınızı ilk LINQ sorgusu](/dotnet/visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query).  
  
 Bir sorgunun sonucu görüntülemek için hata ayıklayıcı onu değerlendirmeniz gerekir. Hata Ayıklayıcısı'ndaki bir LINQ Sorgu sonucunu görüntülediğinizde oluşan bu örtük değerlendirme dikkate almanız gereken bazı etkilere sahiptir:  
  
-   Her değerlendirme sorgusunun zaman alır. Sonuçları düğümü genişletmek zaman alır. Bazı sorgular için yinelenen değerlendirme bir fark edilebilir performans cezası neden olabilir.  
  
-   Bir sorgu değerlendirme veri veya programınız durumunu değerini yapılan değişiklikler yan etkileri neden olabilir. Tüm sorguları yan etkileri olabilir. Bir sorgu güvenle yan etkileri değerlendirilmesi olup olmadığını belirlemek için sorgu uygulayan kod anlamanız gerekir.  
  
##  <a name="BKMK_SteppingAndLinq"></a>Atlama ve LINQ  
 LINQ kod ayıklarken atlama hakkında bilmeniz gereken davranış bazı farklar vardır.  
  
### <a name="linq-to-sql"></a>LINQ - SQL  
 LINQ to SQL sorguları, koşullu hata ayıklayıcı denetimi ötesine kodudur. Bu nedenle, koşul koda adım olamaz. Bir ifade ağacına derler herhangi bir sorgu hata ayıklayıcı denetimi kodu oluşturur.  
  
### <a name="stepping-in-visual-basic"></a>Visual Basic'te Adımlama  
 Bir Visual Basic programımı adımlarken ve bir sorgu bildirimi hata ayıklayıcı karşılaştığında bildirimi içine adım değil ancak tek bir deyimde olarak tüm bildirim vurgular. Bu davranış, çağrılıncaya kadar sorgu değerlendirilmez nedeniyle oluşur. Daha fazla bilgi için bkz: [Visual Basic'te LINQ giriş](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq).  
  
 Aşağıdaki kod örneği adım, hata ayıklayıcı sorgu bildirimi ya da tek bir deyimde olarak sorgu oluşturma vurgular.  
  
```  
Function MyFunction(ByVal x As Char)  
    Return True  
End Function  
  
Sub Main()  
    'Query creation  
    Dim x = From it In "faoaoeua" _  
            Where MyFunction(it) _  
            Select New With {.a = it}  
  
    ' Query execution  
    For Each cur In x  
        Console.WriteLine(cur.ToString())  
    Next  
End Sub  
```  
  
 Yeniden adım, hata ayıklayıcı vurgular `For Each cur In x`. İsteğe bağlı olarak bir sonraki adımda işlevdeki adımları `MyFunction`. Doğruluk sonra `MyFunction`, geri atlar `Console.WriteLine(cur.ToSting())`. Hata ayıklayıcı bu kodu değerlendirmek rağmen herhangi bir noktada, sorgu bildiriminde koşul kodlarda adım.  
  
### <a name="replacing-a-predicate-with-a-function-to-enable-stepping-visual-basic"></a>Bir koşul sürüm (Visual Basic) etkinleştirmek için bir işlev ile değiştirme  
 Varsa hata ayıklama amacıyla koşul kodlarda adım için koşulu özgün doğrulama kodunu içeren bir işlevi çağrısı ile değiştirebilirsiniz. Örneğin, bu kod olduğunu varsayalım:  
  
```  
Dim items() as integer ={1, 2, 3, 4, 5, 6, 7, 8, 9, 10}  
  
' Get the even numbers  
Dim query = From nextInt in items Where nextInt Mod 2 = 0 Select nextInt  
  
For each item in query  
      Console.WriteLine(item)  
Next  
```  
  
 Adlı yeni bir işlev için koşul kod taşıyabilirsiniz `IsEven`:  
  
```  
Dim items () as integer ={1, 2, 3, 4, 5, 6, 7, 8, 9, 10}  
  
' Get the even numbers  
Dim query = From nextInt in items Where IsEven(nextInt) Select nextInt  
  
For each item in query  
      Console.WriteLine(item)  
Next  
...   
Function IsEven(item As =Integer) as Boolean  
      Return item Mod 2 = 0  
End Function  
```  
  
 Düzenlenen sorgu işlevi çağırır `IsEven` her geçişte `items`. Her öğe belirtilen koşulu karşılıyorsa ve kodda aracılığıyla adım olup olmadığını görmek için hata ayıklayıcı windows kullanabilirsiniz `IsEven`. Bu örnekte koşulu oldukça basittir. Ancak, hata ayıklama zorunda daha zor bir koşul varsa, bu teknik çok kullanışlı olabilir.  
  
##  <a name="BKMK_EditandContinueNotSupportedforLINQ"></a>Düzenle ve devam et için LINQ desteklenmiyor  
 Düzenle ve devam et sınırlamaları LINQ sorgularını değişiklikleri destekler. Ayrıntılar için bkz [Çözücü desteklenen değişiklikleri](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits))
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SQL hata ayıklama](http://msdn.microsoft.com/en-us/f27c17e6-1d90-49f2-9fc0-d02e6a27f109)    
 [Özel durumları hata ayıklayıcısı ile yönetme](../debugger/managing-exceptions-with-the-debugger.md)   
 [Giriş LINQ sorgularını (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)   
 [Visual Basic'de LINQ'e giriş](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)