---
title: Yönetici portalı'nda abonelikler düzenlenemedi | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 10/03/2017
ms.topic: Get-Started-Article
description: Yöneticiler abonelik atamaları düzenleme nasıl öğrenin.
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: e4ee209af97d09f5d7e2125d2111746f6fe491f5
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34476644"
---
# <a name="editing-visual-studio-subscription-assignments"></a>Visual Studio abonelik atamalarını düzenlemek

Bir abonelik Yöneticisi olarak kuruluşunuzdaki kişiler atanan aboneliklere değişiklik yapabilirsiniz.  Bu makalede değişiklik yapabilirsiniz ve gerekli adımları sağlar türleri açıklanmaktadır. 

## <a name="making-changes-to-subscriber-information"></a>Abone bilgisi değişiklikler
Hataları düzeltin ya da bilgileri güncelleştirmek için bir abonenin bilgileri düzenleyebilirsiniz. 

Bir abonenin düzenlemek için fare üzerine geldiğinizde abonenin e-posta adresi yanında görüntülenen üç noktaya (...) seçin. Bir açılır listesinde görünür.  Seçin **Düzenle** abonenin ayrıntılarını değiştirmek için. Düzen penceresini açmak üzere Izgara abonenin satırda çift tıklayabilirsiniz.

   <img alt="Select subscriber to edit" src="_img\edit-license\select-subscriber.png" style="border: 1px solid #CCCCCC" />
    
Abonenin ad, Soyadı, ülke, dil ve yüklemeleri güncelleştirebilirsiniz. Abonenin bilgilerini düzenleyin ve ardından **kaydetmek**.

 
   <img alt="Edit subscriber details" src="_img\edit-license\edit-subscriber.png" style="border: 1px solid #CCCCCC" />
   > [!NOTE]
   > Abonelik düzeyinde bir abone için değiştirmeniz gerekiyorsa, Kullanıcı Portalı'ndan silin ve yeniden ekleyin gerekecektir. Abonelik düzeylerini düzenlenebilir değildir.

## <a name="editing-multiple-subscribers-by-using-bulk-edit"></a>Toplu düzenleme kullanarak birden çok aboneye düzenleme

Toplu düzenleme işlemi aynı anda kullanarak birden çok aboneye düzenleyebilirsiniz. Bu özellik, öncelikle şirket oluşturulmak e-posta adresi değişiklikleri veya kuruluş yüklemeleri için erişimi kısıtlamak karar, kuruluşlar için kullanılır. 

   > [!IMPORTANT]
   > Abonelik düzeylerini (yani Enterprise, Professional, vb.) ve abonelik GUID'ler değiştirilemez.  Değiştirilen bu öğeler ile karşıya yükleme çalışırsanız, karşıya yükleme başarısız olur.  

1.  Aynı anda birden çok aboneye düzenlemek için aboneler sekmesine gidin. Üst Şeritte tıklatın **Toplu Düzenle**. 

    <img alt="Editing a License - Bulk Edits" src="_img\edit-license\edit-license-bulk-edit.png" style="border: 1px solid #CCCCCC" />

2.  Toplu düzenleme abone bilgisi düzenlemeleri yapmak için bir Excel şablonu kullanır. Toplu düzenleme kutusuna tıklayın **bu excel verme** tüm kullanıcıların bilgileri de dahil olmak üzere aboneleri geçerli listesini indirmek için. 

    <img alt="Editing a License - Export Bulk Edits List" src="_img\edit-license\edit-license-bulk-edit-export.png" style="border: 1px solid #CCCCCC" />

3.  Ardından, dosyayı kolayca bulmak ve bunu karşıya yüklemeden önce gerekli değişiklikleri yapmak için yerel olarak kaydedin. Başarılı bir karşıya yükleme emin olmak için **abonelik düzeyinde veya abonelik GUID'ini düzenleme yapmadığınız** gibi bunun nedenle karşıya yükleme başarısız olmasına neden olur. 

4.  İade Visual Studio abonelikleri Yönetim Portalı ve toplu Düzenle iletişim kutusunda, tıklatın **Gözat**. Kaydettiğiniz Excel dosyasını tıklatıp **Tamam**. Ekranda karşıya yükleme ilerleme durumunu görürsünüz.

    <img alt="Editing a License - Bulk Edits File Upload" src="_img\edit-license\edit-license-bulk-file-upload1.png" style="border: 1px solid #CCCCCC" />

5.  Dosyayı yüklediğiniz sonra size başarılı olduğunu bildiren bir bildirim görürsünüz. Bu noktada, düzenlemeleriniz abone bilgileri yansıtılır. 

    <img alt="Editing a License - Bulk Edits Upload Complete" src="_img\edit-license\edit-license-bulk-upload-complete.png" style="border: 1px solid #CCCCCC" />

