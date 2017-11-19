---
title: "İzlenecek yol: Kod kusurları için yönetilen kodu analiz etme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code analysis, walkthroughs
- managed code, analyzing
- code analysis tool, walkthroughs
ms.assetid: 22b99f49-1924-4fb5-a421-c8b23e5d5cd4
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3dd0c93476e646895362b98c2f62b569d87ffe35
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-analyzing-managed-code-for-code-defects"></a>İzlenecek yol: Kod Kusurları için Yönetilen Kodu Analiz Etme
Bu kılavuzda, bir yönetilen projenin kod kusurları için kod analizi aracı kullanarak çözümleyin.  
  
 Bu kılavuzda Microsoft .NET Framework tasarım yönergeleri ile uyumluluk için yönetilen .NET kod derlemeleri çözümlemek için Kod Analizi kullanma işlemi adım adım.  
  
 Bu kılavuzda:  
  
-   Analiz etmek ve kod hatası uyarıları düzeltin.  
  
## <a name="prerequisites"></a>Önkoşullar  
  
-   [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)].  
  
## <a name="create-a-class-library"></a>Bir sınıf kitaplığı oluşturun  
  
#### <a name="to-create-a-class-library"></a>Sınıf kitaplığı oluşturmak için  
  
1.  Üzerinde **dosya** menüsünü [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], tıklatın **yeni** ve ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **proje türleri**, tıklatın **Visual C#**.  
  
3.  Altında **şablonları**seçin **sınıf kitaplığı**.  
  
4.  İçinde **adı** metin kutusunda, **CodeAnalysisManagedDemo** ve ardından **Tamam**.  
  
5.  Proje oluşturulduktan sonra Class1.cs dosyasını açın.  
  
6.  Class1.cs varolan metni, aşağıdaki kod ile değiştirin:  
  
     `//CodeAnalysisManagedDemo //Class1.cs using System;  namespace testCode {          public class demo : Exception     {                  public static void Initialize(int size) { }         protected static readonly int _item;         public static int item { get { return _item; } }     } }`  
  
7.  Class1.cs dosyasını kaydedin.  
  
## <a name="analyze-the-project"></a>Proje Çözümle  
  
#### <a name="to-analyze-a-managed-project-for-code-defects"></a>Kod kusurları için yönetilen bir proje çözümlemek için  
  
1.  CodeAnalysisManagedDemo projesinde seçin **Çözüm Gezgini**.  
  
2.  Üzerinde **proje** menüsünde tıklatın **özellikleri**.  
  
     CodeAnalysisManagedDemo özellikleri sayfası görüntülenir.  
  
3.  Tıklatın **CodeAnalysis**.  
  
4.  Olduğundan emin olun **derlemede Kod Analizi etkinleştir (CODE_ANALYSIS sabiti tanımlar**) denetlenir.  
  
5.  Gelen **bu kural kümesini çalıştırmak** aşağı açılan listesinden, **Microsoft tüm kuralları**.  
  
6.  Üzerinde **dosya** menüsünde tıklatın **seçili öğeleri Kaydet**, ManagedDemo özellikler sayfalarına kapatın.  
  
7.  Üzerinde **yapı** menüsünde tıklatın **yapı ManagedDemo**.  
  
     CodeAnalysisManagedDemo proje oluşturma uyarıları dosyasında bildirilen **Kod Analizi** ve **çıkış** windows.  
  
     Varsa **Kod Analizi** penceresi görüntülenmez, üzerinde **Çözümle** menüsünde seçin **Windows** ve ardından **Kod Analizi seçme**.  
  
## <a name="correct-the-code-analysis-issues"></a>Kod Analizi sorunlarını gidermek  
  
#### <a name="to-correct-code-analysis-rule-violations"></a>Kod çözümleme kural ihlallerinin düzeltmek için  
  
1.  Üzerinde **Görünüm** menüsünde tıklatın **hata listesi**.  
  
     Seçtiğiniz Geliştirici profili bağlı olarak, üzerine gerekebilir **diğer pencereler** üzerinde **Görünüm** menüsüne ve ardından **hata listesi**.  
  
2.  İçinde **Çözüm Gezgini**, tıklatın **tüm dosyaları göster**.  
  
3.  Ardından, özellikleri düğümünü genişletin ve sonra AssemblyInfo.cs dosyasını açın.  
  
4.  Uyarıları gidermek için aşağıdakileri kullanın:  
  
-   [CA1014: Derlemeleri CLSCompliantAttribute işaretlemek](../code-quality/ca1014-mark-assemblies-with-clscompliantattribute.md): Microsoft.Design: 'demo' CLSCompliantAttribute ile işaretlenmiş ve değeri true olmalıdır.  
  
    -   Aşağıdaki kodu ekleyip `using``System;` AssemblyInfo.cs dosyasına kayıt yapar.  
  
         Ardından, kod ekleme `[assembly: CLSCompliant(true)]` AssemblyInfo.cs dosyanın sonuna.  
  
         Projeyi yeniden oluşturun.  
  
-   [CA1032: Standart özel durum oluşturucuları uygulayın](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: Bu sınıfına aşağıdaki oluşturucuyu ekleyin: ortak demo(String)  
  
    -   Oluşturucu ekleyin `public demo (String s) : base(s) { }` sınıfına `demo`.  
  
-   [CA1032: Standart özel durum oluşturucuları uygulayın](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: Bu sınıfına aşağıdaki oluşturucuyu ekleyin: ortak demo (dize, özel durum)  
  
    -   Oluşturucu ekleyin `public demo (String s, Exception e) : base(s, e) { }` sınıfına `demo`.  
  
-   [CA1032: Standart özel durum oluşturucuları uygulayın](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: Bu sınıfına aşağıdaki oluşturucuyu ekleyin: tanıtım (SerializationInfo, StreamingContext) korumalı  
  
    -   Aşağıdaki kodu ekleyip `using System.Runtime.Serialization;` Class1.cs dosyası başlangıcına.  
  
         Ardından, bir oluşturucu ekleyin`protected demo (SerializationInfo info, StreamingContext context) : base(info, context) { } to the class demo.`  
  
         Projeyi yeniden oluşturun.  
  
-   [CA1032: Standart özel durum oluşturucuları uygulayın](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: Bu sınıfına aşağıdaki oluşturucuyu ekleyin: ortak demo()  
  
    -   Oluşturucu ekleyin `public demo () : base() { }` sınıfına `demo` **.**  
  
         Projeyi yeniden oluşturun.  
  
-   [CA1709: Tanımlayıcılar doğru ortası](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: ad alanı adı 'testCode' ın büyük/küçük harf 'TestCode' değiştirerek düzeltin.  
  
    -   Ad alanı büyük küçük harf değiştirme `testCode` için `TestCode`.  
  
-   [CA1709: Tanımlayıcılar doğru ortası](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: 'Demo' değiştirerek türü adı 'demo' kasasını düzeltin.  
  
    -   Üyenin adını değiştirmek `Demo`.  
  
-   [CA1709: Tanımlayıcılar doğru ortası](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: üye adı 'öğesini' ın büyük/küçük harf 'Öğesine' değiştirerek düzeltin.  
  
    -   Üyenin adını değiştirmek `Item`.  
  
-   [CA1710: Tanımlayıcılar doğru olmalıdır](../code-quality/ca1710-identifiers-should-have-correct-suffix.md): Microsoft.Naming: '' Nda özel durum' sonlandırmak için yeniden adlandırma testCode.demo'.  
  
    -   Sınıf ve onun kurucusuna adını değiştirmek `DemoException`.  
  
-   [CA2210: Derlemelerin geçerli olmalıdır](../code-quality/ca2210-assemblies-should-have-valid-strong-names.md): 'ManagedDemo' bir güçlü ad anahtar ile oturum açın.  
  
    -   Üzerinde **proje** menüsünde tıklatın **ManagedDemo özellikleri**.  
  
         Proje özellikleri görüntülenir.  
  
         Tıklatın **imzalama**.  
  
         Seçin **derlemeyi imzalamak** onay kutusu.  
  
         İçinde **dize ad anahtar dosyası seç** listesinde  **\<yeni... >**.  
  
         **Güçlü ad anahtarı oluştur** iletişim kutusu görüntülenir.  
  
         İçinde **anahtar dosya adını**, TestKey yazın.  
  
         Bir parola girin ve ardından **Tamam**.  
  
         Üzerinde **dosya** menüsünde tıklatın **seçili öğeleri Kaydet**ve özellik sayfaları kapatın.  
  
         Projeyi yeniden oluşturun.  
  
-   [CA2237: ISerializable türleri SerializableAttribute ile](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md): Microsoft.Usage: 'gösteri' Bu tür ISerializable gerçekleştiren olarak yazmanız için bir [Serializable] özniteliğini ekleyin.  
  
    -   Ekleme `[Serializable ()]` özniteliği sınıfa `demo`.  
  
         Projeyi yeniden oluşturun.  
  
 Değişiklikleri tamamladıktan sonra Class1.cs dosyası aşağıdaki gibi görünmelidir:  
  
```  
//CodeAnalysisManagedDemo  
//Class1.cs  
using System;  
using System.Runtime.Serialization;  
  
namespace TestCode  
{  
  
    [Serializable()]   
    public class DemoException : Exception  
    {  
        public DemoException () : base() { }  
        public DemoException(String s) : base(s) { }  
        public DemoException(String s, Exception e) : base(s, e) { }  
        protected DemoException(SerializationInfo info, StreamingContext context) : base(info, context) { }  
  
        public static void Initialize(int size) { }  
        protected static readonly int _item;  
        public static int Item { get { return _item; } }  
    }  
}  
```  
  
## <a name="exclude-code-analysis-warnings"></a>Kod çözümleme Uyarıları hariç tut  
  
#### <a name="to-exclude-code-defect-warnings"></a>Kod hatası uyarıları dışlamak için  
  
1.  Her kalan uyarılar için aşağıdakileri yapın:  
  
    1.  Kod Analizi penceresinde uyarıyı seçin.  
  
    2.  Seçin **Eylemler**, ardından **bastırmak ileti**ve ardından **proje gizleme dosyasını**.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: menü öğesini kullanarak uyarıları bastırma](../code-quality/how-to-suppress-warnings-by-using-the-menu-item.md)  
  
2.  Projeyi yeniden oluşturun.  
  
     Proje uyarı veya hata oluşturulur.