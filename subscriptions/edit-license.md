---
title: "Yönetici portalı'nda abonelikler düzenlenemedi | Microsoft Docs"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 10/3/2017
Ms.topic: Get-Started-Article
Description: Learn how administrators can edit subscription assignments.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 120bf87ddbaf50efa1abe59bac1c2e4616db7737
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="editing-visual-studio-subscription-assignments"></a>Visual Studio abonelik atamalarını düzenlemek

## <a name="making-changes-to-subscriber-information"></a>Abone bilgisi değişiklikler
Hataları düzeltin ya da bilgileri güncelleştirmek için bir abonenin bilgileri düzenleyebilirsiniz. 
**Bir abonenin e-posta adresini düzenlemek tüm mevcut avantajları sıfırlanması neden olacak unutmayın.**

Bir abonenin düzenlemek için fare üzerine geldiğinizde abonenin e-posta adresi yanında görüntülenen üç noktaya (...) seçin. Bir açılır listesinde görünür.  Seçin **Düzenle** abonenin ayrıntılarını değiştirmek için. Düzen penceresini açmak üzere Izgara abonenin satırda çift tıklayabilirsiniz.

   ![Düzenlemek için abone seçin](_img\edit-license\select-subscriber.png)

Abonenin ad, Soyadı, ülke, dil ve yüklemeleri güncelleştirebilirsiniz. Abonenin bilgilerini düzenleyin ve ardından **kaydetmek**.

   ![Abonelik bilgilerini Düzenle](_img\edit-license\edit-subscriber.png)

> [!NOTE]
> Abonelik düzeyinde bir abone için değiştirmeniz gerekiyorsa, Kullanıcı Portalı'ndan silin ve yeniden ekleyin gerekecektir. Abonelik düzeylerini düzenlenebilir değildir.

## <a name="editing-multiple-subscribers-by-using-bulk-edit"></a>Toplu düzenleme kullanarak birden çok aboneye düzenleme

Toplu düzenleme işlemi aynı anda kullanarak birden çok aboneye düzenleyebilirsiniz. Bu özellik, öncelikle şirket oluşturulmak e-posta adresi değişiklikleri veya kuruluş yüklemeleri için erişimi kısıtlamak karar, kuruluşlar için kullanılır. 

> [!IMPORTANT]
> Abonelik düzeylerini (yani Enterprise, Professional, vb.) ve abonelik GUID'ler değiştirilemez.  Değiştirilen bu öğeler ile karşıya yükleme çalışırsanız, karşıya yükleme başarısız olur.  

1.  Aynı anda birden çok aboneye düzenlemek için aboneler sekmesine gidin. Üst Şeritte tıklatın **Toplu Düzenle**. 

    ![Bir lisans - toplu düzenleme düzenleme](_img\edit-license\edit-license-bulk-edit.png)

2.  Toplu düzenleme abone bilgisi düzenlemeleri yapmak için bir Excel şablonu kullanır. Toplu düzenleme kutusuna tıklayın **bu excel verme** tüm kullanıcıların bilgileri de dahil olmak üzere aboneleri geçerli listesini indirmek için. 

    ![-Lisans Verme düzenleme toplu düzenler listesi](_img\edit-license\edit-license-bulk-edit-export.png)

3.  Ardından, dosyayı kolayca bulmak ve bunu karşıya yüklemeden önce gerekli değişiklikleri yapmak için yerel olarak kaydedin. Başarılı bir karşıya yükleme emin olmak için **abonelik düzeyinde veya abonelik GUID'ini düzenleme yapmadığınız** gibi bunun nedenle karşıya yükleme başarısız olmasına neden olur. 

4.  İade Visual Studio abonelikleri Yönetim Portalı ve toplu Düzenle iletişim kutusunda, tıklatın **Gözat**. Kaydettiğiniz Excel dosyasını tıklatıp **Tamam**. Ekranda karşıya yükleme ilerleme durumunu görürsünüz.

    ![Bir lisans - düzenleme toplu düzenler karşıya dosya yükleme](_img\edit-license\edit-license-bulk-file-upload1.png)

5.  Dosyayı yüklediğiniz sonra size başarılı olduğunu bildiren bir bildirim görürsünüz. 

    ![Bir lisans - düzenleme toplu düzenler karşıya yükleme tamamlandı](_img\edit-license\edit-license-bulk-upload-complete.png)


