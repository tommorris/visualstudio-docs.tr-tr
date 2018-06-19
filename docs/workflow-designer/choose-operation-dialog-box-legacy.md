---
title: İş Akışı Tasarımcısı - işlem iletişim kutusu (eski) seçin
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Workflow.Activities.Design.OperationPickerDialog.UI
ms.assetid: bc3ec902-7797-494e-af48-e70c97eb6779
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fed4353771edc5f9cc1bb239424b0e7015acd84a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31975588"
---
# <a name="choose-operation-dialog-box-legacy"></a>İşlem iletişim kutusu (eski) seçin

Bu konuda açıklanmaktadır kullanma **seçin işlemi** eski Windows iş akışı Tasarımcısı'nda iletişim kutusu. .NET Framework sürüm 3.5 veya WinFX hedeflemek gerektiğinde eski iş akışı Tasarımcısı kullanın.

 **Seçin işlemi** iletişim kutusu ile ilişkilendirilecek bir işlem seçmek amacıyla kullanılan bir <xref:System.Workflow.Activities.ReceiveActivity> etkinlik veya <xref:System.Workflow.Activities.SendActivity> etkinlik. Bu etkinlikler ile bu iletişim kutusunu kullanma hakkında daha fazla bilgi için bkz [nasıl yapılır: uygulama bir WCF sözleşmesi işlemi (eski)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md) ve [nasıl yapılır: bir WCF sözleşmesi işlemi (eski) çağırma](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md).

 Kullanıcı Arabirimi (UI) öğelerini aşağıdaki tabloda açıklanmaktadır **seçin işlemi** iletişim kutusu.

|Arabirim Öğesi|Açıklama|
|----------------|-----------------|
|**Sözleşme Ekle**|Yeni bir sözleşme sizin için oluşturur. Bu sözleşmede yeni işlem tanımlayabilirsiniz. (Bu ile birlikte kullanılan <xref:System.Workflow.Activities.ReceiveActivity> yalnızca.)|
|**Ekleme işlemi**|Yeni işlem içinde oluşturulan yeni bir sözleşme ekler **seçin işlemi** iletişim kutusu. **Not:** yeni işlem aracılığıyla oluşturduğunuz sözleşmeleri ekleyebileceğiniz **seçin işlemi** iletişim kutusu. <br /><br /> (Bu ile birlikte kullanılan <xref:System.Workflow.Activities.ReceiveActivity> yalnızca.)|
|**İçeri Aktar...**|Önceden tanımlanmış bir sözleşme alır ve bir işlem bu sözleşmeden seçmenize olanak sağlar.|
|**İşlem adı**|Şu anda seçili olan işlemin adı. Bu metin kutusu yalnızca bir işlem aracılığıyla oluşturduysanız düzenlemek için kullanılabilir **seçin işlemi** iletişim kutusu.|
|**Parametreler**|Seçili işlem için parametre tanımları içeren sekmesini tıklatın. **Not:** parametre tanımları, yalnızca bir işlem aracılığıyla oluşturduysanız değiştirilebilir **seçin işlemi** iletişim kutusu.|
|**Özellikler**|Sekme içeren <xref:System.Net.Security.ProtectionLevel> hizmet ve istemci arasında gönderilen iletiler için ayarları. **Not:** Bu sekme yalnızca bir işlem aracılığıyla oluşturduysanız etkin **seçin işlemi** iletişim kutusu.|
|**İzinler**|Sekme içeren <xref:System.Workflow.Activities.OperationInfoBase.PrincipalPermissionName%2A> ve <xref:System.Workflow.Activities.OperationInfoBase.PrincipalPermissionRole%2A> bu işlem çağırmak için izin verilen kullanıcıların özelliklerini. Yalnızca Yöneticiler grubundan kullanıcıların bu işlemi çağırmak için izin verilen, örneğin, daha sonra "Yöneticiler" yazarsınız **rol** metin kutusu.<br /><br /> Bu sekme aracılığıyla oluşturulan iki işlem için etkin **ChooseOperation** iletişim kutusu ve üzerinden aktarılan işlemleri **alma** düğmesi.|

> [!NOTE]
> **Seçin işlemi** iletişim kutusu, yalnızca sözleşmeleri veya diğer tarafından kullanılan işlemleri gösterir <xref:System.Workflow.Activities.SendActivity> iş akışı etkinlikleri. Benzer şekilde, **seçin işlemi** iletişim kutusu için <xref:System.Workflow.Activities.ReceiveActivity> etkinlikleri yalnızca sözleşmeleri veya diğer tarafından kullanılan işlemleri gösterir **ReceiveActivity** iş akışı etkinlikleri.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: uygulama bir WCF sözleşmesi işlemi (eski)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)
- [Nasıl yapılır: bir WCF sözleşmesi işlemi (eski) çağırma](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)
- [Windows Workflow Foundation Kullanıcı Arabirimi Yardımı için Eski Tasarımcı](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)