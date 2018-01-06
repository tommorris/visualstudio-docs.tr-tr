---
redirect_url: /visualstudio/csharp-ide/refactoring/extract-interface
title: "Ayıklama arabirimi yeniden düzenlemesi (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- refactoring [C#], Extract Interface
- Extract Interface refactoring operation [C#]
ms.assetid: 7d0aa225-3b33-4331-9652-5a67cac6f3d0
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: e3e606a86f5989ca928e0b093b564f997f92a559
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="extract-interface-refactoring-c"></a>Ayıklama Arabirimi Yeniden Düzenlemesi (C#)
Ayıklama, bir varolan sınıf, yapı veya arabirim kaynaklanan üyelere sahip yeni bir arabirim oluşturmak için kolay bir yol sağlayan bir yeniden düzenleme işlemi arabirimidir.  
  
 Çeşitli istemciler aynı alt üyelerinin bir sınıf, yapı ya da arabirimi kullandığınızda veya birden çok sınıflar, yapılar veya arabirimler üyelerin bir alt kümesini ortak sahip olduğunuzda, bir arabirim üye alt kümesini gerçekleştirir yararlı olabilir. Arabirimleri kullanma hakkında daha fazla bilgi için bkz: [arabirimleri](/dotnet/csharp/programming-guide/interfaces/index).  
  
 Ayıklama arabirimi yeni bir dosyada bir arabirim oluşturur ve imleci yeni dosyanın başına yerleştirir. Yeni arabirimi, yeni arabirimin adını ve kullanarak oluşturulan dosya adı ayıklamak için hangi üyeleri belirtebilirsiniz **arayüz** iletişim kutusu.  
  
### <a name="to-use-extract-interface"></a>Ayıklama arabirimi kullanmak için  
  
1.  Adlı bir konsol uygulaması oluşturun `ExtractInterface`ve ardından Değiştir `Program` aşağıdaki kodla  
  
    ```csharp  
    // Invoke Extract Interface on ProtoA.  
    // Note:  the extracted interface will be created in a new file.  
    class ProtoA  
    {  
        public void MethodB(string s) { }  
    }  
    ```  
  
2.  İçinde bulunan imleç ile `MethodB`, tıklatıp **arayüz** üzerinde **yeniden düzenlemeniz** menüsü.  
  
     **Arayüz** iletişim kutusu görüntülenir.  
  
     Klavye kısayolu CTRL + R, ı görüntülemek için de yazabilirsiniz **arayüz** iletişim kutusu.  
  
     Ayrıca farenin sağ işaret **yeniden düzenlemeniz**ve ardından **arayüz** görüntülemek için **arayüz** iletişim kutusu.  
  
3.  Tıklatın **Tümünü Seç**.  
  
4.  **Tamam**'ı tıklatın.  
  
     Yeni dosya, IProtoA.cs ve aşağıdaki kodu bakın:  
  
    ```csharp  
    using System;  
    namespace TopThreeRefactorings  
    {  
        interface IProtoA  
        {  
            void MethodB(string s);  
        }  
    }  
    ```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özellik yalnızca, imleç sınıf, yapı veya ayıklamak istediğiniz üyeleri içeren arabirimi konumlandırıldığında erişilebilir. İmleci bu konumda olduğunda, arayüz yeniden düzenleme işlemi çağırır.  
  
 Ayıklama arabirimi bir sınıf veya yapı çağırdığınızda tabanları ve arabirimler listesi yeni arabirimin adını içerecek şekilde değiştirilir. Extract bir arabirimde çağırdığınızda tabanları ve arabirimler listesi değiştirilmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yeniden düzenlemesi (C#)](refactoring-csharp.md)