---
title: 'CA2000: Kapsamı kaybetmeden önce verileri atın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2000
- Dispose objects before losing scope
- DisposeObjectsBeforeLosingScope
helpviewer_keywords:
- CA2000
- DisposeObjectsBeforeLosingScope
ms.assetid: 0c3d7d8d-b94d-46e8-aa4c-38df632c1463
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6b492324b87bfc25741492669b7c659c43fc9765
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31920411"
---
# <a name="ca2000-dispose-objects-before-losing-scope"></a>CA2000: Kapsamı kaybetmeden önce verileri atın
|||
|-|-|
|TypeName|DisposeObjectsBeforeLosingScope|
|CheckId|CA2000|
|Kategori|Microsoft.Reliability|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Yerel bir nesne bir <xref:System.IDisposable> türü oluşturulur ancak nesne yapılan tüm başvuruları kapsamının dışına önce nesne atıldı değil.

## <a name="rule-description"></a>Kural Tanımı
 Önce tüm başvuruları kapsamının dışında bir seferlik nesne açıkça atıldı değil, nesne atık toplayıcı nesnesi sonlandırıcıyı çalıştığında belirsiz bir süre sonra silinecek. Olağanüstü bir olay oluşabilecek olduğundan, engeller sonlandırıcıyı çalışmasını nesnesinin nesne açıkça yerine atılmalıdır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için arama <xref:System.IDisposable.Dispose%2A> nesnesindeki önce tüm başvuruları kapsam dışındadır.

 Kullanabileceğiniz Not `using` deyimi (`Using` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) uygulayan nesneler sarmalamak için `IDisposable`. Bu şekilde kaydırılan nesneler otomatik olarak atıldı kapanışında `using` bloğu.

 Bazı durumlarda şunlardır burada deyimiyle IDisposable nesnelerini korumak yeterli değildir ve CA2000 oluşmasına neden olabilir.

-   Bir seferlik nesnesi döndüren gerektirir nesnesi kullanarak bir dışında bir try/finally bloğu içinde oluşturulur bloğu.

-   Tek kullanımlık bir nesnenin üyelerine başlatma yapılmamalıdır oluşturucu kullanılarak yapılan bir ifade.

-   Yalnızca bir özel durum işleyici tarafından Korumalı Oluşturucular iç içe geçme. Örneğin,

    ```csharp
    using (StreamReader sr = new StreamReader(new FileStream("C:\myfile.txt", FileMode.Create)))
    { ... }
    ```

     CA2000 StreamReader nesne yapımı içinde bir hata hiçbir zaman kapatılan FILESTREAM nesnesinde sağladığından oluşmasına neden olur.

-   Dinamik nesneler IDisposable nesnelerin Dispose desen uygulamak için bir gölge nesnesi kullanmanız gerekir.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Nesnenizde `Dispose` gibi <xref:System.IO.Stream.Close%2A> çağıran bir yöntem çağırmadığınız sürece veya uyarıyı oluşturan yöntem nesnenizi sarmalayan bir IDisposable nesnesi getirmediği sürece bu kuraldan bir uyarıyı bastırmayın.

## <a name="related-rules"></a>İlgili kuralları
 [CA2213: Atılabilen alanlar atılmalıdır](../code-quality/ca2213-disposable-fields-should-be-disposed.md)

 [CA2202: Nesneleri birden çok kez atmayın](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)

## <a name="example"></a>Örnek
 Bir seferlik nesnesi döndüren bir yöntem uyguluyorsanız, nesne atıldı emin olmak için bir try/finally bloğu bir catch bloğunun olmadan kullanın. Try/finally bloğu kullanarak hataya noktada oluşturulması ve bu nesne atıldı emin olmak özel durumlar izin verin.

 OpenPort1 yönteminde ISerializable nesneyi seri bağlantı noktası açmak için arama veya SomeMethod çağrısı başarısız olabilir. Bu uygulama üzerinde CA2000 uyarı tetiklenir.

 OpenPort2 yönteminde iki seri bağlantı noktası nesneler bildirilen ve ayarlanmış null şunlardır:

-   `tempPort`, yöntemi işlemleri başarılı olduğunu test etmek için kullanılır.

-   `port`, yönteminin dönüş değeri için kullanılır.

 `tempPort` Oluşturulur ve açılır bir `try` bloğu ve diğer gerekli iş aynı gerçekleştirilir `try` bloğu. Sonunda `try` bloğu, açılan bağlantı noktası atanması `port` döndürülecek nesne ve `tempPort` nesne ayarlanmış `null`.

 `finally` Blok denetler değerini `tempPort`. Null değilse, yöntemi bir işlem başarısız oldu, ve `tempPort` tüm kaynakları serbest bırakılır emin olmak için kapalı. Verilen bağlantı noktası nesnesi yöntemi işlemleri başarılı ya da bir işlem başarısız olursa null olur açılmış seri bağlantı noktası nesne içerir.

```csharp
public SerialPort OpenPort1(string portName)
{
   SerialPort port = new SerialPort(portName);
   port.Open();  //CA2000 fires because this might throw
   SomeMethod(); //Other method operations can fail
   return port;
}

public SerialPort OpenPort2(string portName)
{
   SerialPort tempPort = null;
   SerialPort port = null;
   try
   {
      tempPort = new SerialPort(portName);
      tempPort.Open();
      SomeMethod();
      //Add any other methods above this line
      port = tempPort;
      tempPort = null;

   }
   finally
   {
      if (tempPort != null)
      {
         tempPort.Close();
      }
   }
   return port;
}
```

```vb
Public Function OpenPort1(ByVal PortName As String) As SerialPort

   Dim port As New SerialPort(PortName)
   port.Open()    'CA2000 fires because this might throw
   SomeMethod()   'Other method operations can fail
   Return port

End Function


Public Function OpenPort2(ByVal PortName As String) As SerialPort

   Dim tempPort As SerialPort = Nothing
   Dim port As SerialPort = Nothing

   Try
      tempPort = New SerialPort(PortName)
      tempPort.Open()
      SomeMethod()
      'Add any other methods above this line
      port = tempPort
      tempPort = Nothing

   Finally
      If Not tempPort Is Nothing Then
         tempPort.Close()
      End If


   End Try

   Return port

End Function
```

## <a name="example"></a>Örnek
 Varsayılan olarak, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] derleyici sahip tüm aritmetik işleçler için taşma denetleyin. Bu nedenle, herhangi bir Visual Basic aritmetik işlem throw bir <xref:System.OverflowException>. Bu kuralları CA2000 gibi beklenmeyen ihlali neden olabilir. Örneğin, Visual Basic derleyici StreamReader değil çıkarılması neden olacağından bir özel durum oluşturabilir eklenmesi için yönerge denetimi taşma yayma çünkü aşağıdaki CreateReader1 işlevi CA2000 ihlaline neden olur.

 Bu sorunu gidermek için Visual Basic derleyici projenizdeki tarafından taşma denetimleri yayma devre dışı bırakabilir veya kodunuzu aşağıdaki CreateReader2 işlevi olduğu gibi değiştirebilirsiniz.

 Taşma denetimleri yayma devre dışı bırakmak için Çözüm Gezgini'nde proje adına sağ tıklayın ve ardından **özellikleri**. ' I tıklatın **derleme**, tıklatın **Gelişmiş derleme seçenekleri**ve ardından denetleyin **kaldırmak tamsayı taşma denetimleri**.

  [!code-vb[FxCop.Reliability.CA2000.DisposeObjectsBeforeLosingScope#1](../code-quality/codesnippet/VisualBasic/ca2000-dispose-objects-before-losing-scope-vboverflow_1.vb)]

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.IDisposable> [Desen dispose](/dotnet/standard/design-guidelines/dispose-pattern)