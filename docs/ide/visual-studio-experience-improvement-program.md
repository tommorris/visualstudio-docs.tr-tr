---
title: Müşteri Deneyimi Geliştirme Programı
description: Visual Studio'da gizlilik ayarlarının nasıl yönetileceğini öğrenin.
ms.date: 05/21/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
author: PoulChapman
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d4558e086ec53aa0e264fd55a322d4b5acaac7aa
ms.sourcegitcommit: cc88ccc6aacebe497899fab05d243a65053e194c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
---
# <a name="visual-studio-customer-experience-improvement-program"></a>Visual Studio Müşteri Deneyimini Geliştirme Programı

Visual Studio Müşteri Deneyimi Geliştirme Programı (VSCEIP), zaman içinde Visual Studio geliştirmesine yardımcı olmak için tasarlanmış bir programdır. Bu program bilgisayar donanımıyla ve kişiler Visual Studio, kullanıcıların bilgisayardaki görevlerini kesintiye uğratmadan kullanma hakkında bilgi toplar. Toplanan bilgiler, Microsoft'un hangi özellikleri iyileştireceğini belirlemesine yardımcı olur. Bu belge içinde veya dışında VSCEIP opt alınmaktadır.

## <a name="opt-in-or-out"></a>Giriş veya çıkış iptal et

VSCEIP varsayılan olarak açıktır. Kapatın veya, bu yönergeleri izleyerek yeniden açın:

1. Visual Studio'yu başlatın.

1. Gelen **yardımcı** menüsündeki **geri bildirim gönder**ve ardından **ayarları**.

   **Visual Studio Deneyimini Geliştirme Programı** iletişim kutusu açılır.

1. Geri çevirmek için seçin **Hayır, katılmak istiyorum değil**ve ardından **Tamam**.
   Kabul için seçin **Evet, katılmak istiyorum**ve ardından **Tamam**.

   ![Visual Studio Deneyimini Geliştirme Programı iletişim](media/experience-improvement-program.png)

### <a name="registry-settings"></a>Kayıt defteri ayarları

Yüklerseniz [derleme araçları Visual Studio için](https://www.visualstudio.com/downloads/#build-tools-for-visual-studio-2017), VSCEIP yapılandırmak için kayıt defterini güncelleştirmeniz gerekir. Kurumsal müşteriler, kayıt defteri tabanlı bir ilke ayarlayarak içinde veya dışında VSCEIP kabul etmek için bir Grup İlkesi oluşturabilirsiniz.

[!INCLUDE [gdpr-hybrid-note](../misc/includes/gdpr-hybrid-note.md)]

İlgili kayıt defteri anahtarı ve ayarlar aşağıdaki gibidir:

Anahtar = **HKEY_CURRENT_USER\SOFTWARE\Microsoft\VSCommon\15.0\SQM**

Giriş OptIn =

Değer = (DWORD)
- **0** alma (VSCEIP Kapat) seçti
- **1** (VSCEIP etkinleştirin) seçti

> [!CAUTION]
> Kayıt defterinin hatalı düzenlenmesi sisteminize ciddi şekilde zarar verebilir. Kayıt defterinde değişiklik yapmadan önce, bilgisayarınızdaki tüm değerli verileri yedeklemelisiniz. Aynı zamanda **bilinen son iyi yapılandırma** el ile yapılan değişiklikler uygulandıktan sonra sorunlarla karşılaşırsanız başlangıç seçeneği.

İşlenen veya aktarılan VSCEIP tarafından toplanan, bilgileri hakkında daha fazla bilgi için bkz [Microsoft gizlilik bildirimi](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Ayrıca bkz.

* [Bizimle iletişime geçin](../ide/talk-to-us.md)
* [Visual Studio ile ilgili bir sorun bildirme](../ide/how-to-report-a-problem-with-visual-studio-2017.md)
* [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/)
* [Microsoft gizlilik bildirimi](https://privacy.microsoft.com/privacystatement)