---
title: "Kod parçacıkları için en iyi uygulamalar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code snippets, best practices
- code snippets, security
ms.assetid: a293ec17-4dd7-4a99-8eeb-99f44a822a8b
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 34424ae13a47008eaefa3634f2bf25d31daf285e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="best-practices-for-using-code-snippets"></a>Kod Parçacıkları İçin En İyi Uygulamalar
Kod parçacığı kodda bir şeyler yalnızca en temel yolu gösterir. Çoğu uygulama için kod uygulama uyacak şekilde değiştirilmesi gerekir.  
  
## <a name="handling-exceptions"></a>Özel Durumları İşleme  
 Genellikle, kod parçacığında Try... Catch blokları yakalamak ve tüm özel durumları yeniden oluşturma. Projeniz için doğru seçim olabilir. Her özel durum için yanıt birkaç yolu vardır. Örnekler için bkz: [nasıl yapılır: bir özel durum try/catch kullanarak (C# programlama Kılavuzu) işleme](/dotnet/csharp/programming-guide/exceptions/how-to-handle-an-exception-using-try-catch) ve [deneyin... Catch... Finally ifadesi](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement).  
  
## <a name="file-locations"></a>Dosya konumları  
 Dosya konumları uygulamanıza uyum, aşağıdakiler hakkında düşünün:  
  
-   Erişilebilir bir konumda bulunuyor. Uygulama dosyaların dosya depolama çalışmayabilir böylece kullanıcılar bilgisayar Program dosyaları klasörü için erişiminiz olmayabilir.  
  
-   Güvenli bir konumda bulunuyor. Kök klasöründe dosyaların depolanması (C:\\) güvenli değildir. Uygulama verileri için \Application veri klasörü öneririz. Bireysel kullanıcı verileri için uygulama \My Belgeler klasöründe her kullanıcı için bir dosya oluşturabilirsiniz.  
  
-   Geçerli bir dosya adı kullanıyor. Kullanabileceğiniz <xref:System.Windows.Forms.OpenFileDialog> ve <xref:System.Windows.Forms.SaveFileDialog> geçersiz dosya adları olasılığını azaltmak için denetimleri. Kullanıcı bir dosyayı seçtiğinde ve kodunuzu dosyasını yöneten saat arasında dosya silinebilir unutmayın. Ayrıca, kullanıcı dosyaya yazmak için izni olmayabilir.  
  
## <a name="security"></a>Güvenlik  
 Ne kadar güvenli bir parçası olduğu kaynak kodunda kullanıldığı ve kodda olduğunda nasıl değiştirilir bağlıdır. Aşağıdaki listede birkaç dikkate alınmalıdır alanları içerir.  
  
-   Dosya ve veritabanı erişimi  
  
-   Kod erişimi güvenliği  
  
-   Kaynakları koruma (olay günlükleri gibi kayıt defteri)  
  
-   Gizli anahtarları depolama  
  
-   Girişleri doğrulanıyor  
  
-   Komut dosyası teknolojilerini veri geçirme  
  
 Daha fazla bilgi için bkz: [güvenli hale getirme uygulamaları](../ide/securing-applications.md).  
  
## <a name="downloaded-code-snippets"></a>İndirilen kod parçacıkları  
 IntelliSense kod parçacıkları Visual Studio tarafından yüklenen kendileri bir tehlike değildir. Ancak, bunlar uygulamanızda güvenlik riskleri oluşturabilirsiniz. Internet'ten indirilen parçacıkları herhangi diğer indirilen içeriği gibi - onaylamadığından çok dikkatli olunmalıdır.  
  
-   Yalnızca güvendiğiniz sitelerinden parçacıkları indirin ve güncel virüs yazılımı kullanın.  
  
-   Tüm indirilen parçacık dosyaları Not Defteri veya Visual Studio XML düzenleyicisinde açın ve yüklemeden önce dikkatle gözden geçirin. Aşağıdaki sorunları arayın:  
  
    -   Bunu yürütüyorsa parçacığı kod sisteminize zarar verebilir. Kaynak kodu çalıştırmadan önce dikkatle okuyun.  
  
    -   Parçacık dosyasını Yardım URL'si bloğunu bir kötü amaçlı komut dosyası yürütme ya da rahatsız edici bir Web sitesini görüntülemek URL'leri içerebilir.  
  
    -   Kod parçacığını sessizce projenize eklenir ve sisteminizdeki her yerden yüklenebilir başvurular içeriyor. Bu başvuruları bilgisayarınıza kod parçacığını indirdiğiniz gelen indirildi. Kod parçacığını sonra bir yöntemine yapılan bir çağrı kötü amaçlı kod yürüten başvurusunda kalmasına neden olabilir. Böyle bir saldırıya karşı korunmak için parçacık dosyasını içeri aktarmalar ve başvuruları bloklarını gözden geçirin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Basic IntelliSense kodu parçacıkları](/dotnet/visual-basic/developing-apps/using-ide/intellisense-code-snippets)   
 [Uygulamalarının güvenliğini sağlama](../ide/securing-applications.md)   
 [Kod parçacıkları](../ide/code-snippets.md)