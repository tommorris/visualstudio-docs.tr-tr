---
title: Excel Communicator Arabirimi Örnekleme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: sample
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 88aa282a2e742ffff53582fd4855d06e3a06db69
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="sample-excel-communicator-interface"></a>Excel Communicator Arabirimi Örnekleme
Örnek `IExcelUICommunication` arabirimi kullanılır `ExcelUICommunicator` nesnesinde `ExcelAddIn` projesi.

## <a name="iexceluicommunication-interface"></a>IExcelUICommunication arabirimi
 Bu arabirim arasındaki iletişim noktalarını tanımlar `CodedUIExtension`, kodlanmış UI testi işleminde çalışır ve `ExcelCodedUIAddIn`, çalışan [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] işlemi.

 `ExcelCodedUIAddinHelper` Derleme sahip bir `ExcelUICommunicator` bu arabirimden oluşan ve Excel nesne modeli yöntemleri işlemek için kullandığı sınıf.

 Bazı yöntemler Excel'den istenen bilgileri alın ardından oluşturup gibi bilgileri birini nesneleri dönmek `CellInformation` nesnesi.

 Diğer yöntemleri sağlanan bilgi nesnesini kullanın, karşılık gelen denetim Excel'de bulun ve bazı işlem denetimi gerçekleştirin. Örneğin, `ScrollIntoView` yöntemi kayar çalışma belirlenen hücrenin görünür olmasını sağlayın.

## <a name="codeduiextensibilitysample-and-excelcodeduiaddinhelper-communication"></a>CodedUIExtensibilitySample ve ExcelCodedUIAddinHelper iletişim
 `ExcelCodedUIAddinHelper` Derleme Excel işleminde çalışır ve olan `UICommunicator` uygulayan sınıf `IExcelUITestCommunication` arabirim ve alır veya gerekli bilgileri doğrudan Excel Arabiriminden ayarlar.

 `CodedUIExtensibilitySample` Derleme Visual Studio Kodlanmış UI Test işleminde çalışır. Bu derleme sahip `Communicator` bir .NET uzaktan iletişim kanal açar ve sağlayan sınıf bir `Instance` kullanan özelliği `IExcelUICommunication` kullanılacak arabirimi `UICommunicator` nesnesinde `ExcelCodedUIAddinHelper` istekleri ve bilgileri geçirmek için derleme nesneleri, gibi bir `CellInformation` iki derleme arasında ileri ve geri nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

- [Kodlanmış Kullanıcı Arabirimi Testlerini ve Eylem Kayıtlarını Microsoft Excel'i Desteklemek için Genişletme](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
- [Kodlanmış UI Testi için Excel Eklenti Örneği](../test/sample-excel-add-in-for-coded-ui-testing.md)
- [Excel için Kodlanmış UI Testi Uzantısı Örneği](../test/sample-coded-ui-test-extension-for-excel.md)
