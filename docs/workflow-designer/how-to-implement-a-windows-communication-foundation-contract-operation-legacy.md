---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: uygulama bir Windows Communication Foundation sözleşmesi işlemi (eski)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: d6aeb20e-fac8-4a9d-bd26-ae78bef96b41
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0b069d8ca8c1adb72e2869eb59644e8abeff14ae
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-implement-a-windows-communication-foundation-contract-operation-legacy"></a>Nasıl yapılır: uygulama bir Windows Communication Foundation sözleşmesi işlemi (eski)

Bu konuda hedefleyen eski Windows iş akışı Tasarımcısı'nı kullanarak bir Windows Communication Foundation (WCF) sözleşme işlemi uygulamak .NET Framework sürüm 3.5 veya WinFX açıklar.

Sürükleme sonra bir **ReceiveActivity** araç etkinliğinden iş akışı tasarım yüzeyine ya da oluşturduğunuz yeni bir [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] sözleşme veya var olan bir sözleşmeyi alma ve işlemler uygulayın. Seçin ve/veya sizin oluşturup aracılığıyla işlemlerini [seçin işlem iletişim kutusu (eski)](../workflow-designer/choose-operation-dialog-box-legacy.md).

## <a name="to-implement-a-wcf-contract-operation"></a>Bir WCF sözleşmesi işlemi uygulamak için

1.  Çift **ReceiveActivity** etkinlik Tasarımcısı'nda veya yanındaki üç nokta düğmesini tıklatın **ServiceOperationInfo** özelliğinde **özellikleri** bölmesi.

2.  Aşağıdakilerden birini yapın:

    -   Tıklatın **ekleme Sözleşme** iletişim kutusunun sağ üst köşedeki. Bu yeni bir oluşturacak [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] sözleşme ve sizin için işlem.

         -veya-

    -   Tıklatın **alma** iletişim kutusunun sağ üst köşedeki. [Göz atın ve bir .NET türünü seç iletişim kutusu (eski)](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box-legacy.md) açar. Bir derlemeyi ya da istediğiniz sözleşme içeren projesi arayın. Sözleşme seçin ve tıklatın **Tamam**.

     Bir sözleşme oluşturulan veya içeri sonra yeni işlemler için oluşturulan veya içeri aktarılan sözleşme ekleyebilirsiniz. Yeni işlem eklemek, sözleşmeyi seçin ve **ekleme işlemi** iletişim kutusunun sağ üst köşedeki. Ekleme işlemleri tamamladığınızda, 3. adıma geçin.

3.  İle ilişkilendirmek istediğiniz işlemi seçin **ReceiveActivity** etkinlik. İşlem adı, parametreleri, özellikleri ve izin ayarlarını değiştirerek işlemi tanımını yönetebilirsiniz.

     Adını değiştirmek için yeni adı girin **işlem adı** metin kutusu.

     Tıklatın **parametreleri** işlem parametreleri erişmek için sekme. Ad, tür veya bir parametre yönünü değiştirmek yanı sıra ekleyebilir veya işlemi parametreleri silebilirsiniz.

     Tıklatın **özellikleri** işlemi işlemi koruma düzeyi ve desteklenen ileti exchange işlevselliğini erişmek için sekme.

     Tıklatın **izinleri** sekmesinde hangi gruplara işlemi uygulamak için izin verildiğini belirtmek için.

4.  Tıklatın **Tamam** ve **ReceiveActivity** etkinlik uyguladığı işlemi için işlem adı görüntülenir.

5.  Bulacağınızı içinde bu işlemi uygulanması için kullanılacak iş akışı etkinlikleri yerleştirin **ReceiveActivity** etkinlik.

## <a name="see-also"></a>Ayrıca bkz.

- [İşlem Seç İletişim Kutusu (Eski)](../workflow-designer/choose-operation-dialog-box-legacy.md)
- [Nasıl yapılır: bir WCF sözleşmesi işlemi (eski) çağırma](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)
- [Eski İş Akışı Etkinlikleri ](../workflow-designer/legacy-workflow-activities.md)