---
redirect_url: /visualstudio/csharp-ide/refactoring/encapsulate-field
title: "Alanı Yalıt yeniden düzenleme (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- Encapsulate Field refactoring operation [C#]
- refactoring [C#], Encapsulate Field
ms.assetid: bf714a04-ab1e-49ce-99ce-dda1ebb1a17f
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: d587edebcea443e0bfff52004b128c70923470d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="encapsulate-field-refactoring-c"></a>Alan Yeniden Düzenlemesini Yalıtma (C#)
**Yalıt** yeniden düzenleme işlemi özellik varolan bir alandan hızlı bir şekilde oluşturmak ve ardından sorunsuz bir şekilde kodunuzu yeni özellik başvuruları güncelleştirin olanak sağlar.  
  
 Zaman bir [alan](/dotnet/csharp/programming-guide/classes-and-structs/fields) olan [ortak](/dotnet/csharp/language-reference/keywords/public), diğer nesneleri bu alana doğrudan erişimi vardır ve bu alana sahip olan nesne tarafından algılanamadı bunu değiştirebilirsiniz. Kullanarak [özellikleri](/dotnet/csharp/programming-guide/classes-and-structs/properties) o alanı kapsüllemek için alanları doğrudan erişimi engelleyebilirsiniz.  
  
 Yeni özellik oluşturmak için **Yalıt** işlemi için kapsüllemek istediğiniz bir alan için erişim değiştiricisi değiştirir [özel](/dotnet/csharp/language-reference/keywords/private)ve ardından oluşturur [almak](/dotnet/csharp/language-reference/keywords/get)ve [ayarlamak](/dotnet/csharp/language-reference/keywords/set) erişimciler Bu alan için. Bazı durumlarda, yalnızca bir `get` erişimci oluşturulur, ne zaman alan salt okunur bildirilmiş gibi.  
  
 Belirtilen alanları yeni özelliğinde başvuruları kodunuzu yeniden düzenleme Altyapısı güncelleştirmeleri **güncelleştirme başvuruları** bölümünü **Yalıt** iletişim kutusu.  
  
### <a name="to-create-a-property-from-a-field"></a>Bir özellik alandan oluşturmak için  
  
1.  Adlı bir konsol uygulaması oluşturun `EncapsulateFieldExample`ve ardından Değiştir `Program` aşağıdaki kod örneği ile.  
  
    ```csharp  
    class Square  
    {  
        // Select the word 'width' and then use Encapsulate Field.  
        public int width, height;  
    }  
    class MainClass  
    {  
        public static void Main()  
        {  
            Square mySquare = new Square();  
            mySquare.width = 110;  
            mySquare.height = 150;  
            // Output values for width and height.  
            Console.WriteLine("width = {0}", mySquare.width);  
            Console.WriteLine("height = {0}", mySquare.height);  
        }  
    }  
    ```  
  
2.  İçinde [Kod düzenleyicisinde](../ide/writing-code-in-the-code-and-text-editor.md), imleç bildiriminde kapsüllemek istediğiniz alanın adını yerleştirin. Aşağıdaki örnekte imleci word yerleştirin `width`:  
  
    ```csharp  
    public int width, height;  
    ```  
  
3.  Üzerinde **yeniden düzenlemeniz** menüsünde tıklatın **Yalıt**.  
  
     **Yalıt** iletişim kutusu görüntülenir.  
  
     CTRL + R, görüntülenecek E klavye kısayolu da yazabilirsiniz **Yalıt** iletişim kutusu.  
  
     Ayrıca, imleci sağ işaret **yeniden düzenlemeniz**ve ardından **Yalıt** görüntülemek için **Yalıt** iletişim kutusu.  
  
4.  Ayarlarını belirtin.  
  
5.  ENTER tuşuna basın veya tıklatın **Tamam** düğmesi.  
  
6.  Seçtiyseniz **başvuru değişikliklerini Önizleme** seçeneği, sonra **başvuru değişikliklerini Önizleme** penceresi açılır. Tıklatın **Uygula** düğmesi.  
  
     Aşağıdaki `get` ve `set` erişimci kodu kaynak dosyanızda görüntülenir:  
  
    ```csharp  
    public int Width  
    {  
        get { return width; }  
        set { width = value; }  
    }  
    ```  
  
     Kodda `Main` yöntemi de güncelleştirilmiştir yeni `Width` özellik adı.  
  
    ```csharp  
    Square mySquare = new Square();  
    mySquare.Width = 110;  
    mySquare.height = 150;  
    // Output values for width and height.  
    Console.WriteLine("width = {0}", mySquare.Width);  
    ```  
  
## <a name="remarks"></a>Açıklamalar  
 **Yalıt** işlemi yapıldığında yalnızca imleç alan bildirimiyle aynı satırda konumlandırıldı.  
  
 Birden çok alan bildirme bildirimleri **Yalıt** alanlar arasında sınır olarak virgül kullanır ve imlecin en yakın olan alanın ve imleci aynı satır yeniden düzenleme başlatır. Bu alanın adını bildiriminde seçerek kapsüllemek istediğiniz alanı de belirtebilirsiniz.  
  
 Bu yeniden düzenleme işlemi tarafından oluşturulan kodu yalıtma alan kod parçacıkları özelliği tarafından modellenir. Kod parçacıkları değiştirilebilir. Daha fazla bilgi için bkz: [kod parçacıkları](../ide/visual-csharp-code-snippets.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yeniden düzenlemesi (C#)](refactoring-csharp.md)   
 [Visual C# Kod Parçacıkları](../ide/visual-csharp-code-snippets.md)