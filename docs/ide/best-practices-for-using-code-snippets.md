---
title: Kod Parçacıkları İçin En İyi Uygulamalar
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code snippets, best practices
- code snippets, security
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 52845b2d8f08486f84422957ce8f38a95c1a4d31
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="best-practices-for-using-code-snippets"></a>Kod parçacıkları için en iyi uygulamalar

Kod parçacığı kodda bir şeyler yalnızca en temel yolu gösterir. Çoğu uygulama için kod uygulama uyacak şekilde değiştirilmesi gerekir.

## <a name="handling-exceptions"></a>Özel durumları işleme

Genellikle, kod parçacığında Try... Catch blokları yakalamak ve tüm özel durumları yeniden oluşturma. Projeniz için doğru seçim olabilir. Her özel durum için yanıt birkaç yolu vardır. Örnekler için bkz: [nasıl yapılır: try/catch (C#) kullanarak bir özel durum işleme](/dotnet/csharp/programming-guide/exceptions/how-to-handle-an-exception-using-try-catch) ve [deneyin... Catch... Finally deyimi (Visual Basic)](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement).

## <a name="file-locations"></a>Dosya konumları

Dosya konumları uygulamanıza uyum, aşağıdakiler hakkında düşünün:

- Erişilebilir bir konumda bulunuyor. Kullanıcılar, erişimi olmayabilir *Program Files* uygulamayla dosyaların depolanması may iş dosyaları değil, böylece bilgisayarının klasör.

- Güvenli bir konumda bulunuyor. Kök klasöründe dosyaların depolanması (*C:\\*) güvenli değildir. Uygulama verileri için öneririz *uygulama verilerini* klasör. Bireysel kullanıcı verileri için uygulamayı her kullanıcı için bir dosya oluşturabilirsiniz *belgeleri* klasör.

- Geçerli bir dosya adı kullanıyor. Kullanabileceğiniz <xref:System.Windows.Forms.OpenFileDialog> ve <xref:System.Windows.Forms.SaveFileDialog> geçersiz dosya adları olasılığını azaltmak için denetimleri. Kullanıcı bir dosyayı seçtiğinde ve kodunuzu dosyasını yöneten saat arasında dosya silinebilir unutmayın. Ayrıca, kullanıcı dosyaya yazmak için izni olmayabilir.

## <a name="security"></a>Güvenlik

Ne kadar güvenli bir parçası olduğu kaynak kodunda kullanıldığı ve kodda olduğunda nasıl değiştirilir bağlıdır. Aşağıdaki listede birkaç dikkate alınmalıdır alanları içerir.

- Dosya ve veritabanı erişimi

- Kod erişimi güvenliği

- Kaynakları koruma (olay günlükleri gibi kayıt defteri)

- Gizli anahtarları depolama

- Girişleri doğrulanıyor

- Komut dosyası teknolojilerini veri geçirme

Daha fazla bilgi için bkz: [uygulamalarının güvenliğini sağlama](../ide/securing-applications.md).

## <a name="downloaded-code-snippets"></a>İndirilen kod parçacıkları

IntelliSense kod parçacıkları Visual Studio tarafından yüklenen kendileri bir tehlike değildir. Ancak, bunlar uygulamanızda güvenlik riskleri oluşturabilirsiniz. Internet'ten indirilen parçacıkları herhangi diğer indirilen içeriği gibi - onaylamadığından çok dikkatli olunmalıdır.

- Yalnızca güvendiğiniz sitelerinden parçacıkları indirin ve güncel virüs yazılımı kullanın.

- Tüm indirilen parçacık dosyaları Not Defteri veya Visual Studio XML düzenleyicisinde açın ve yüklemeden önce dikkatle gözden geçirin. Aşağıdaki sorunları arayın:

    - Bunu yürütüyorsa parçacığı kod sisteminize zarar verebilir. Kaynak kodu çalıştırmadan önce dikkatle okuyun.

    - Parçacık dosyasını Yardım URL'si bloğunu bir kötü amaçlı komut dosyası yürütme ya da rahatsız edici bir Web sitesini görüntülemek URL'leri içerebilir.

    - Kod parçacığını sessizce projenize eklenir ve sisteminizdeki her yerden yüklenebilir başvurular içeriyor. Bu başvuruları bilgisayarınıza kod parçacığını indirdiğiniz gelen indirildi. Kod parçacığını sonra bir yöntemine yapılan bir çağrı kötü amaçlı kod yürüten başvurusunda kalmasına neden olabilir. Böyle bir saldırıya karşı korunmak için parçacık dosyasını içeri aktarmalar ve başvuruları bloklarını gözden geçirin.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Basic IntelliSense kod parçacıkları](/dotnet/visual-basic/developing-apps/using-ide/intellisense-code-snippets)
- [Uygulamalarının güvenliğini sağlama](../ide/securing-applications.md)
- [Kod parçacıkları](../ide/code-snippets.md)