---
redirect_url: /visualstudio/csharp-ide/refactoring/extract-method
title: "Ayıklama yöntemi yeniden düzenlemesi (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- refactoring [C#], Extract Method
- Extract Method refactoring operation [C#]
ms.assetid: eeba11df-a815-4bec-9c21-8a831891b783
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 18fc4c20b39341f884fb23b51822ce7f6e427007
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="extract-method-refactoring-c"></a>Ayıklama Yöntemi Yeniden Düzenlemesi (C#)
**Ayıklama yöntemi** yeni bir yöntem var olan bir üye kodu parçadaki oluşturmak için kolay bir yol sağlayan yeniden düzenleme bir işlemdir.  
  
 Kullanarak **ayıklama yöntemi**, varolan bir üyenin kod bloğunun kodunun seçimi çıkartarak yeni bir yöntem oluşturabilirsiniz. Yeni, ayıklanan yöntem seçili kodu içerir ve mevcut üyedeki seçili kod yeni yöntemine bir çağrı ile değiştirilir. Kendi yönteminin içine kod parçacığını kapatma hızla olanak tanır ve doğru bir şekilde daha iyi yeniden kullanma ve okunabilirliği kodunu yeniden düzenleyin.  
  
 **Ayıklama yöntemi** aşağıdaki faydaları vardır:  
  
-   Ayrık, yeniden kullanılabilir yöntemleri vurgulayarak en iyi kodlama uygulamalarını teşvik etmektedir.  
  
-   Kod iyi kuruluş aracılığıyla kendi kendine belgeleme önerir.  
  
     Açıklayıcı adlar kullanılan, üst düzey yöntemleri olduğunda daha fazla bilgi için bir seri açıklama gibi.  
  
-   Geçersiz kılma basitleştirmek için yöntemleri geçirmiş oluşturulmasını önerir.  
  
-   Kod yinelemesinden azaltır.  
  
### <a name="to-use-extract-method"></a>Ayıklama yöntemi kullanmak için  
  
1.  Adlı bir konsol uygulaması oluşturun `ExtractMethod`ve ardından Değiştir `Program` aşağıdaki kod örneği ile.  
  
    ```csharp  
    class A  
    {  
        const double PI = 3.141592;  
  
        double CalculatePaintNeeded(double paintPerUnit, double radius)  
        {  
            // Select any of the following:  
            // 1. The entire next line of code.  
            // 2. The right-hand side of the next line of code.  
            // 3. Just "PI *" of the right-hand side of the next line  
            //    of code (to see the prompt for selection expansion).  
            // 4.  All code within the method body.  
            // ...Then invoke Extract Method.  
  
            double area = PI * radius * radius;  
  
            return area / paintPerUnit;  
        }  
    }  
    ```  
  
2.  Ayıklamak istediğiniz kod parçası seçin:  
  
    ```csharp  
    double area = PI * radius * radius;  
    ```  
  
3.  Üzerinde **yeniden düzenlemeniz** menüsünde tıklatın **ayıklama yöntemi**.  
  
     **Ayıklama yöntemi** iletişim kutusu görüntülenir.  
  
     Alternatif olarak, ayrıca CTRL + R, görüntülenecek M klavye kısayolunu yazabilirsiniz **ayıklama yöntemi** iletişim kutusu.  
  
     Ayrıca seçili tıklayabilir kod, işaret **yeniden düzenlemeniz**ve ardından **ayıklama yöntemi** görüntülemek için **ayıklama yöntemi** iletişim kutusu.  
  
4.  Yeni bir yöntem için bir ad belirtin `CircleArea`, **yeni yöntem adı** kutusu.  
  
     Yeni yöntemi imza önizlemesini görüntüler altında **Önizleme yöntem imzası**.  
  
5.  **Tamam**'ı tıklatın.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullandığınızda **ayıklama yöntemi** komutu, yeni yöntemi, aynı sınıfta kaynak üyenin eklenir.  
  
## <a name="partial-types"></a>Kısmi türler  
 Sınıfı kısmi bir tür ise **ayıklama yöntemi** kaynak üye hemen ardından yeni yöntemi oluşturur. **Ayıklama yöntemi** örnek veri yeni yöntemi kod tarafından başvurulduğunda statik bir yöntem oluşturarak yeni bir yöntem imzası belirler.  
  
## <a name="generic-type-parameters"></a>Genel Tür Parametreleri  
 Kısıtlanmamış genel tür parametresi var. bir yöntem ayıkladığınızda, oluşturulan kod eklemeyecek `ref` değiştiricisi Bu parametre için bir değer atanmış sürece. Ayıklanan yöntemi genel tür bağımsız değişkeni olarak başvuru türleri destekleyecek sonra el ile eklemeniz gerekir `ref` değiştirici yöntem imzası parametre.  
  
## <a name="anonymous-methods"></a>Anonim Yöntemler  
 Ardından Visual Studio, bildirilen veya anonim yöntemin dışında başvurulan yerel bir değişken için bir başvuru içeren bir anonim yöntemi parçası genişletmeye çalışırsanız, olası anlamsal değişiklikler hakkında uyarır.  
  
 Anonim yöntemi yerel bir değişkenin değerini kullandığında, değer anonim yöntem yürütüldüğü şu anda elde edilir. Adsız bir yöntem başka bir yönteme ayıklandığında yerel değişkenin değerini Ayıklanmış yöntem çağrısı anda elde edilir.  
  
 Aşağıdaki örnek anlamsal değişikliği gösterir. Bu kod, yürütülürse **11** konsola yazdırılır. Kullanırsanız **ayıklama yöntemi** kendi yönteminin içine kod yorumları tarafından işaretlenmiş kod bölgesini ayıklamak ve işlenmiş kodu sonra yürütmek için **10** konsola yazdırılır.  
  
```csharp  
class Program  
{  
    delegate void D();  
    D d;  
    static void Main(string[] args)  
    {  
        Program p = new Program();  
        int i = 10;  
        /*begin extraction*/  
            p.d = delegate { Console.WriteLine(i++); };  
        /*end extraction*/  
        i++;  
        p.d();  
    }  
}  
```  
  
 Bu durumu çözmek için sınıf anonim yöntemi alanlarında kullanılan yerel değişkenler olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yeniden düzenlemesi (C#)](refactoring-csharp.md)