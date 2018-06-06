---
title: C++ için Visual Studio veri araçları
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CPP
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
- cplusplus
ms.openlocfilehash: d2e74fca7109a19c789215424526eef6190b568c
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752404"
---
# <a name="visual-studio-data-tools-for-c"></a>C++ için Visual Studio veri araçları

Veri kaynaklarına erişirken yerel C++ genellikle hızlı performans sağlar. Ancak, Visual Studio'da C++ uygulamaları için tooling veri .NET uygulamaları için olduğu gibi zengin değil. Örneğin, veri kaynaklarını windows sürükle ve bırak C++ tasarım yüzeyine veri kaynakları için kullanılamaz. Nesne ilişkisel bir katman gerekiyorsa, kendi yazmak veya bir üçüncü taraf ürünü kullanmak gerekir.  Bellek verileri depolamak ve kullanıcıya görüntülemek için Microsoft Foundation Class Kitaplığı kullanan uygulamalar belgeler ve görünümler, birlikte bazı veritabanı sınıfları kullanmanız mümkün olmakla birlikte aynı veri bağlama işlevselliği için geçerlidir. Daha fazla bilgi için bkz: [Visual C++'da veri erişimi](/cpp/data/data-access-in-cpp).

SQL veritabanlarına bağlanmak için yerel C++ uygulamaları ODBC ve OLE DB sürücüleri ve Windows ile birlikte ADO sağlayıcısı kullanabilirsiniz. Bunlar bu arabirimleri destekleyen herhangi bir veritabanı bağlanabilir. ODBC sürücüsü standardıdır. OLE DB geriye dönük uyumluluk için sağlanır. Bu veri teknolojileri hakkında daha fazla bilgi için bkz: [Windows Data Access Components](https://msdn.microsoft.com/library/windows/desktop/aa968814.aspx).

SQL Server 2005'te özel işlevsellikten yararlanmak ve daha sonra kullanmak için [SQL Server Native Client](/sql/relational-databases/native-client/sql-server-native-client). Yerel İstemcisi ayrıca SQL Server ODBC sürücüsü ve bir yerel dinamik bağlantı kitaplığı (DLL) SQL Server OLE DB Sağlayıcısında içerir. Bunlar, Microsoft SQL Server için yerel kodlu API'ler (ODBC, OLE DB ve ADO) kullanan uygulamaları destekler.  SQL Server Native Client SQL Server veri araçları ile yükler. Programlama Kılavuzu şöyledir: [SQL Server yerel istemci programlama](/sql/relational-databases/native-client/sql-server-native-client-programming).

## <a name="to-connect-to-localdb-through-odbc-and-sql-native-client-from-a-c-application"></a>Bir C++ uygulamasından localDB ODBC ve SQL Native Client aracılığıyla bağlanmak için

1.  SQL Server veri Araçları'nı yükleyin.

2.  Bağlanmak için örnek bir SQL veritabanı gerekiyorsa, Northwind veritabanı indirin ve yeni bir konuma sıkıştırmasını açın.

3.  Yerel veritabanına sıkıştırması açılmış Northwind.mdf dosya eklemek için SQL Server Management Studio kullanın. SQL Server Management Studio başladığında (localdb) \MSSQLLocalDB bağlayın.

     ![İletişim SSMS bağlanma](../data-tools/media/raddata-ssms-connect-dialog.png)

     Ardından sol bölmedeki localdb düğümünü sağ tıklatın ve seçin **Attach**.

     ![Veritabanı SSMS ekleme](../data-tools/media/raddata-ssms-attach-database.png)

4.  ODBC Windows SDK'sı örneği indirin ve yeni bir konuma sıkıştırmasını açın. Bu örnek bir veritabanı ve sorunu sorgulara ve komutlara için bağlanmak için kullanılan temel ODBC komutları gösterir. Bu işlevler hakkında daha fazla bilgiyi [Microsoft açık veritabanı bağlantısı (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc). (Bu C++ klasörüdür) çözümü ilk yüklediğinizde, Visual Studio çözümü Visual Studio'nun geçerli sürümüne yükseltmek sunar. **Evet**'i tıklayın.

5.  Yerel istemci kullanmak için lib dosya ve üstbilgi dosyası gerekir. Bu dosyalar, İşlevler ve sql.h içinde tanımlanan ODBC işlevleri ötesinde SQL Server'a özel tanımları içerir. İçinde **proje** > **özellikleri** > **VC ++ dizinleri**, aşağıdakileri içeren dizin ekleyin:

**%ProgramFiles%\Microsoft SQL Server\110\SDK\Include**

Ve bu kitaplık dizini:

**%ProgramFiles%\Microsoft SQL Server\110\SDK\Lib**

6.  Bu satırlar odbcsql.cpp ekleyin. #Define ilgisiz OLE DB tanımları derlenmiş engeller.

    ```cpp
    #define _SQLNCLI_ODBC_
    #include <sqlncli.h>
    ```

    Yukarıdaki adımları derlemek ve çalıştırmak için gerekli olmayan örnek gerçekte yerel istemci işlevlerden herhangi birini kullanmadığından olduğunu unutmayın. Ancak projeyi şimdi bu işlevi kullanmak için yapılandırıldı. Daha fazla bilgi için bkz: [SQL Server yerel istemci programlama](/sql/relational-databases/native-client/sql-server-native-client).

7.  ODBC alt sisteminde kullanmak için hangi sürücü belirtebilirsiniz. Örnek sürücü bağlantı dizesi özniteliği bir komut satırı bağımsız değişkeni geçirir. İçinde **proje** > **özellikleri** > **hata ayıklama**, bu komut bağımsız değişkeni ekleyin:

    ```cpp
    DRIVER="SQL Server Native Client 11.0"
    ```

8.  Derleme ve uygulamayı çalıştırmak için F5 tuşuna basın. Bir veritabanı girmenizi ister sürücü iletişim kutusundan görmeniz gerekir. Girin `(localdb)\MSSQLLocalDB`ve denetleme **güvenilir bağlantı kullan**. Press **OK**. Konsolu, başarılı bir bağlantı belirten iletileri ile görmeniz gerekir. Ayrıca, bir komut istemi SQL deyiminde yazabileceğiniz da görmeniz gerekir. Aşağıdaki ekran örnek bir sorgu ve sonuçları gösterilmektedir:

     ![ODBC örnek sorgu çıktısı](../data-tools/media/raddata-odbc-sample-query-output.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da verilere erişime](../data-tools/accessing-data-in-visual-studio.md)