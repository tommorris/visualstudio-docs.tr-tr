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
ms.openlocfilehash: 57338d465710e608079bf289db4516de46a88277
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
---
# <a name="visual-studio-customer-experience-improvement-program"></a>Visual Studio Müşteri Deneyimini Geliştirme Programı

Visual Studio Müşteri Deneyimi Geliştirme Programı (VSCEIP), zaman içinde Visual Studio geliştirmesine yardımcı olmak için tasarlanmıştır. Bu program [hatalar hakkında bilgi toplar](../ide/diagnostic-data-collection.md), bilgisayar donanımı ve kullanıcıların bilgisayardaki görevlerini kesintiye uğratmadan kişi Visual Studio nasıl kullanır. Toplanan bilgiler, Microsoft'un hangi özellikleri iyileştireceğini belirlemesine yardımcı olur. Bu belge içinde veya dışında VSCEIP opt alınmaktadır.

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

* [Visual Studio tarafından toplanan tanılama bilgileri](diagnostic-data-collection.md)
* [Bizimle iletişime geçin](../ide/talk-to-us.md)
* [Visual Studio ile ilgili bir sorun bildirme](../ide/how-to-report-a-problem-with-visual-studio-2017.md)
* [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/)
* [Microsoft gizlilik bildirimi](https://privacy.microsoft.com/privacystatement)