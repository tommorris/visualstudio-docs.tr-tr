---
redirect_url: /visualstudio/csharp-ide/refactoring/rename
title: "Yeniden düzenlemesi (C#) yeniden adlandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- refactoring [C#], Rename
- Rename refactoring [C#]
ms.assetid: 268942fc-b142-4dfa-8d90-bedd548c2e4f
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 42c5f99b3bf5ba95bc279cd5e117745ccc8e02c3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="rename-refactoring-c"></a>Yeniden Düzenlemeyi (C#) yeniden adlandırma
**Yeniden Adlandır** kod sembolleri alanları, yerel değişkenleri, yöntemleri, ad alanları, özellikleri ve türleri gibi tanımlayıcıları yeniden adlandırmak için kolay bir yol sağlar Visual Studio tümleşik geliştirme ortamını (IDE) yeniden düzenleme bir özelliktir. **Yeniden Adlandır** açıklamaları ve dizeleri adlarını değiştirmek ve bildirimler ve bir tanımlayıcı çağrıları değiştirmek için kullanılabilir.  
  
> [!NOTE]
>  Yeniden adlandırma düzenlemesi gerçekleştirmeden önce kaynak denetimi için Visual Studio kullanırken, kaynakları en son sürümünü alın.  
  
 Yeniden adlandırma düzenlemesi aşağıdaki Visual Studio özelliklerinden kullanılabilir:  
  
|Özellik|IDE içinde yeniden düzenleme davranışı|  
|-------------|----------------------------------------|  
|Kod Düzenleyicisi|Belirli türde bir kod simgeleri imleci getirdiğinizde Kod Düzenleyicisi'nde, yeniden adlandırma düzenlemesi kullanılabilir. İmleci bu konumda olduğunda, çağırabileceği **yeniden adlandırma** klavye kısayolu (Ctrl + R, Ctrl + R) yazarak veya seçerek komutu **yeniden adlandırma** hızlı Eylemler, kısayol menüsünde komutunu veya **Yeniden düzenlemeniz** menüsü.|  
|Sınıf Görünümü|Sınıf Görünümü'nde tanımlayıcı seçtiğinizde, yeniden adlandırma düzenlemesi kısayol menüsünden kullanılabilir ve **yeniden düzenlemeniz** menüsü.|  
|Nesne Tarayıcısı|Nesne tarayıcısında tanımlayıcı seçtiğinizde, yeniden adlandırma düzenlemesi yalnızca kullanılabilir **yeniden düzenlemeniz** menüsü.|  
|Windows Form Tasarımcısı'nın özellik Kılavuzu|İçinde **özellik Kılavuzu** Windows Forms Tasarımcısı, bir denetim adının değiştirilmesi bu denetim için bir yeniden adlandırma işlemi başlatır. **Yeniden adlandırma** iletişim kutusunda görüntülenmez.|  
|Çözüm Gezgini|İçinde **Çözüm Gezgini**, **yeniden adlandırma** komutu kısayol menüsünde kullanılabilir. Seçilen kaynak dosyası sınıf adı dosya adı ile aynı olan bir sınıf içeriyorsa, aynı anda kaynak dosyayı yeniden adlandırın ve yeniden adlandırma düzenlemesi yürütmek için bu komutu kullanabilirsiniz.<br /><br /> Örneğin, varsayılan Windows tabanlı bir uygulama oluşturun ve sonra Form1.cs TestForm.cs için yeniden adlandırın, kaynak dosya adı Form1.cs TestForm.cs ve Form1 sınıfı değiştirir ve tüm başvuruları sınıfı için TestForm adlandırılacak. **Not:** **geri** komutu (CTRL + Z) yalnızca kodda yeniden adlandırma düzenlemesi geri ve dosya adı özgün adına geri değiştiremez olur. <br /><br /> Seçilen kaynak dosyanın adı dosya adı ile aynı olan bir sınıf içermiyorsa **yeniden adlandırma** komutunu **Çözüm Gezgini** yalnızca kaynak dosyayı yeniden adlandırır ve yeniden adlandırma çalıştırmaz yeniden düzenleme.|  
  
## <a name="rename-operations"></a>İşlemleri yeniden adlandırın.  
 Çalıştırdığınızda **yeniden adlandırma**, aşağıdaki tabloda açıklandığı şekilde yeniden düzenleme altyapısı her kod simgesi için belirli bir yeniden adlandırma işlemi gerçekleştirir.  
  
|Kod simgesi|İşlemi yeniden adlandırın.|  
|-----------------|----------------------|  
|Alan|Bildirimler ve alanı kullanımlar yeni ad ile değiştirir.|  
|Yerel değişken|Bildirimler ve değişken kullanımları yeni ad ile değiştirir.|  
|Yöntem|Yöntemin adı ve bu yöntem tüm başvuruları yeni ad ile değiştirir. **Not:** bir genişletme yöntemi yeniden adlandırdığınızda, yeniden adlandırma işlemi kapsamında genişletme yöntemi statik bir yöntem veya örnek yöntemi olarak kullanılıp kullanılmadığını bağımsız olarak yöntemi tüm örneklerini yayar. Daha fazla bilgi için bkz: [genişletme yöntemleri](/dotnet/csharp/programming-guide/classes-and-structs/extension-methods).|  
|Ad Alanı|Ad alanı bildirimi içinde yeni ad değişikliklerini tüm `using` deyimleri ve tam olarak nitelenmiş adlar. **Not:** bir ad alanı adlandırırken [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] de güncelleştirir **varsayılan Namespace** özelliği **uygulama** sayfasında **Proje Tasarımcısı**. Bu özellik seçerek sıfırlanamaz **geri** gelen **Düzenle** menüsü. Sıfırlamak için **varsayılan Namespace** özellik değerini değiştirmeniz gerekir özelliğinde **Proje Tasarımcısı**. Daha fazla bilgi için bkz: [uygulama sayfası](../ide/reference/application-page-project-designer-csharp.md).|  
|Özellik|Bildirimler ve kullanımları özelliğinin yeni ad ile değiştirir.|  
|Tür|Tüm bildirimler ve türündeki tüm kullanımları oluşturucular ve yok ediciler dahil yeni ad ile değiştirir. Kısmi türler için yeniden adlandırma işlemi için tüm bölümleri yayılır.|  
  
#### <a name="to-rename-an-identifier"></a>Bir tanımlayıcı yeniden adlandırmak için  
  
1.  Adlı bir konsol uygulaması oluşturun `RenameIdentifier`ve ardından Değiştir `Program` aşağıdaki kod örneği ile.  
  
    ```csharp  
    class ProtoClassA  
    {  
        // Invoke on 'MethodB'.  
        public void MethodB(int i, bool b) { }  
    }  
  
    class ProtoClassC  
    {  
        void D()  
        {  
            ProtoClassA MyClassA = new ProtoClassA();  
  
            // Invoke on 'MethodB'.  
            MyClassA.MethodB(0, false);  
        }  
    }  
    ```  
  
2.  İmleç Yerleştir `MethodB`, yöntem bildirimi veya yöntem çağrısı.  
  
3.  Gelen **yeniden düzenlemeniz** menüsünde, select **yeniden adlandırma**. **Yeniden adlandırma** iletişim kutusu görüntülenir.  
  
     Ayrıca imleci sağ işaret **yeniden düzenlemeniz** bağlam menüsünü ve ardından **yeniden adlandırmak** görüntülemek için **yeniden adlandırma** iletişim kutusu.  
  
4.  İçinde **yeni bir ad** alanı, tür `MethodC`.  
  
5.  Seçin **açıklamaları aramada** onay kutusu.  
  
6.  **Tamam**'ı tıklatın.  
  
7.  İçinde **Değişiklikleri Önizle** iletişim kutusu, tıklatın **Uygula**.  
  
#### <a name="to-rename-an-identifier-using-quick-actions"></a>Hızlı eylemleri kullanarak bir tanımlayıcı yeniden adlandırmak için  
  
1.  Adlı bir konsol uygulaması oluşturun `RenameIdentifier`ve ardından Değiştir `Program` aşağıdaki kod örneği ile.  
  
    ```csharp  
    class ProtoClassA  
    {  
        // Invoke on 'MethodB'.  
        public void MethodB(int i, bool b) { }  
    }  
  
    class ProtoClassC  
    {  
        void D()  
        {  
            ProtoClassA MyClassA = new ProtoClassA();  
  
            // Invoke on 'MethodB'.  
            MyClassA.MethodB(0, false);  
        }  
    }  
    ```  
  
2.  Öğesinin bildiriminde `MethodB`yazın veya geri yöntemi tanımlayıcı. Hızlı Eylemler ampul kenar boşluğunda görünür.  
  
    > [!NOTE]
    >  Yalnızca bir tanımlayıcı bildirimi hızlı Eylemler kullanarak yeniden adlandırma düzenlemesi de çalıştırabilirsiniz.  
  
3.  Klavye kısayolu yazın **Shift + Alt + F10** hızlı Eylemler menüsü görüntülemek için.  
  
     veya  
  
     Siyah üçgen ampul hızlı Eylemler menüsü görüntülemek için İleri'yi tıklatın.  
  
4.  Seçin **yeniden adlandırma '\<identifer1 >' için '\<identifier2 >'** yeniden adlandırma düzenlemesi çağrılacak menü öğesi. Tüm başvuruları  **\<identifer1 >** otomatik olarak güncelleştirilecek  **\<identifier2 >**.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="renaming-implemented-or-overridden-members"></a>Uygulanan veya geçersiz kılınan üye yeniden adlandırma  
 Olduğunda, **yeniden adlandırma** , uygulamalar/geçersiz kılmalar veya uygulanan/geçersiz kılınmış diğer türlerde üyeleri tarafından üyesi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yeniden adlandırma işlemi basamaklı güncelleştirmeleri neden olacak bildiren bir iletişim kutusu görüntüler. Tıklatırsanız **devam**, yeniden düzenleme altyapısı yinelemeli olarak bulur ve tüm üyelerin Base yeniden adlandırır ve türetilmiş türleri uygulayan/geçersiz kılmalar ilişkileri adı değiştirilmekte olan üye.  
  
 Aşağıdaki kod örneğinde uygulamalar/geçersiz kılmalar ilişkileri üyeleriyle içerir.  
  
 [!code-csharp[CsUsingCsIDERefactor#1](../csharp-ide/codesnippet/CSharp/rename-refactoring-csharp_1.cs)]  
  
 Önceki örnekte, yeniden adlandırma `C.Method()` de yeniden adlandırır `Ibase.Method()` çünkü `C.Method()` uygulayan `Ibase.Method()`. Ardından, yeniden düzenleme altyapısı yinelemeli, görür `Ibase.Method()` tarafından uygulanan `Derived.Method()` ve yeniden adlandırır `Derived.Method()`. Yeniden düzenleme motoru yeniden adlandırmayın `Base.Method()`, çünkü `Derived.Method()` geçersiz `Base.Method()`. Sahip olduğunuz sürece düzenleme motoru burada durur **yeniden adlandırmak aşırı** iade **yeniden adlandırma** iletişim kutusu.  
  
 Varsa **yeniden adlandırmak aşırı** denetlenir düzenleme motoru yeniden adlandırır `Derived.Method(int i)` çünkü `Derived.Method()`, `Base.Method(int i)` tarafından geçersiz olduğundan `Derived.Method(int i)`, ve `Base.Method()` bir aşırı yüklemesini olduğundan `Base.Method(int i)`.  
  
> [!NOTE]
>  Başvurulan bütünleştirilmiş kodunda tanımlandığına üyesi yeniden adlandırdığınızda, yeniden adlandırma derleme hataları neden olacak bir iletişim kutusu açıklanmaktadır.  
  
## <a name="renaming-properties-of-anonymous-types"></a>Anonim türdeki özellikleri yeniden adlandırma  
 Anonim türler özelliğinde yeniden adlandırdığınızda, yeniden adlandırma işlemi aynı özelliklere sahip anonim diğer türleri özelliklerinde yayılır. Aşağıdaki örnekler, bu davranış gösterir.  
  
```csharp  
var a = new { ID = 1};  
var b = new { ID = 2};  
```  
  
 Önceki kodda, yeniden adlandırma `ID` değiştirecek `ID` hem deyimlerinde aynı temel anonim tür sahip oldukları için.  
  
```csharp  
var companyIDs =  
    from c in companylist  
    select new { ID = c.ID, Name = c.Name};  
  
var orderIDs =  
    from o in orderlist  
    select new { ID = o.ID, Item = o.Name};  
```  
  
 Önceki kodda, yeniden adlandırma `ID` yalnızca tek bir örneğini adlandıracak `ID` çünkü `companyIDs` ve `orderIDs` aynı özelliklere sahip değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yeniden düzenlemesi (C#)](refactoring-csharp.md)   
 [Anonim Tipler](/dotnet/csharp/programming-guide/classes-and-structs/anonymous-types)