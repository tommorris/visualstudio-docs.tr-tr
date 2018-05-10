---
title: TF sürüm denetimi
description: Team Foundation Server veya Visual Studio Team Services Team Foundation sürüm denetimi ile bağlanma.
author: asb3993
ms.author: amburns
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: f892209faeb06ca703d28016457e9ba4ab86ccda
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="connecting-to-team-foundation-version-control"></a>Team Foundation sürüm denetimi bağlama 

Visual Studio Team Services (VSTS) ve Team Foundation Server (TFS) iki modeli sürüm denetimi sağlar: dağıtılan Git sürüm denetimi ve Team Foundation sürüm denetimi (olan TFVC'yi), sürüm denetimi Merkezi. Mac için Visual Studio ile Team Foundation sürüm denetimi kullanmak için bu makalede genel bir bakış ve bir başlangıç noktası sağlar

> [!NOTE]
> **Not**: Team Foundation sürüm denetimi desteği şu anda önizlemede ve bazı işlevler henüz tam olarak çalışmıyor. Daha fazla değişiklik gelmesini hala!

## <a name="requirements"></a>Gereksinimler

* Mac 7.5 veya sonraki bir sürümü için Visual Studio.
* Visual Studio Team sunucuları veya Team Foundation Server 2013 ve üstü
* Visual Studio Team Services veya Team Foundation Server, Team Foundation sürüm denetimi kullanmak üzere yapılandırılmış bir proje.

## <a name="installation"></a>Yükleme

Mac için Visual Studio içinde arasından **Visual Studio > uzantıları...**  menüsü. Arama "TF sürüm denetimi için" ve yükleme **Team Foundation sürüm denetimi** uzantısı. IDE istendiğinde yeniden başlatın.

## <a name="using-the-add-in"></a>Eklenti kullanma

Uzantısı yüklendikten sonra Seç **sürüm denetimi > TFS/VSTS > Team Foundation sürüm denetimi Bağlan...**  menüsü. 

![TFVC'yi sunucu ekleme](media/tfvc-add-remove-server.png)


Visual Studio Team Services veya Team Foundation Server başlamak için seçin:

![TFVC'yi Server ile bağlanma](media/tfvc-choose-server-type.png)

Kimlik bilgilerini girin: 

![TFVC'yi sunucuya oturum açın](media/tfvc-login.png)

Ardından, erişmek istediğiniz projeleri seçin: 

![Projeleri seçin](media/tfvc-choose-projects.png)

Devam etmek için iletişim kutularını kapatın ve daha sonra kullanmak için **sürüm denetimi > TFS/VSTS > Kaynak Denetim Gezgini** kaynak menüsünü kullanın.

> [!WARNING]
> **Bilinen sorun**: önizleme sürümünü ilk kez, Kaynak Denetim Gezgini'ni açmak, yeni bir çalışma alanı oluşturmak zorunda kalırsınız.

![Kaynak Gezgini](media/tfvc-source-explorer.png)

Kaynak kodu Gezgini'nden sunucuda, kaynak kodu bulun ve aşağıdaki eylemleri gerçekleştirin:

- Çalışma alanları (Oluştur, Düzenle veya Sil) yönetin.
- Proje yapısı arasında gidin.
- Projeleri eşleyin.
- Projeleri alın.
- Kilit & Unlock dosyaları.
- Dosyalarını yeniden adlandırın.
- Dosyaları silin.
- Yeni dosya ekleyin.
- Kontrol etme.
- Teslim etme.
- Geçmiş değişiklikleri görüntüleyin.
- Değişiklikleri karşılaştırın.

## <a name="creating-a-new-workspace"></a>Yeni bir çalışma alanı oluşturma

Kaynak Denetim Gezgini tıklayın **çalışma alanlarını yönet** düğmesi. 

![Çalışma alanlarını yönet](media/tfvc-manage-workspaces.png)

Tıklayın **Ekle** yeni bir çalışma alanı oluşturmak için.

![Çalışma alanı oluşturma](media/tfvc-create-workspace.png)

Çalışma alanı için bir ad sağlayın ve ardından **çalışma klasörü Ekle** proje bilgisayarınızdaki yerel bir klasöre eşleştirmek için.

İşiniz bittiğinde, tıklatın **Tamam**, çalışma alanlarını yönet iletişim kutusunu kapatın. Artık dosyaları kaynak kod Gezgini ancak almak ve başlamak hazırsınız.