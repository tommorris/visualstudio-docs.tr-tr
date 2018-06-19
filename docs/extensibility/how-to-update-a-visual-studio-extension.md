---
title: 'Nasıl yapılır: Visual Studio uzantısı güncelleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- update package
- update extension
- new package version
ms.assetid: 93f79774-7b79-4dd6-94ad-13698f72c257
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c37f26ed8215bb7eac360c978ba902c8e95975ba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134688"
---
# <a name="how-to-update-a-visual-studio-extension"></a>Nasıl yapılır: Visual Studio uzantısı güncelleştir
Kullanarak bir Visual Studio uzantısı sisteminizde güncelleştirebilirsiniz **Uzantılar ve güncelleştirmeler** güncelleştirilmiş sürümünü yüklemek için. Uzantı güncelleştirilmiş bir sürümünü oluşturursanız, belirtmek VSIX bildiriminde sürüm numarası artırılarak güncelleştirilmiş gibi.  
  
 Güncelleştirmeler, gelen uzantısını VSIX bildirimi aynı olduğunda yüklenir `ID` yüklü bir ve daha yüksek olarak `Version` numarası. Varsa `Version` sayıdır aynı veya daha düşükse paket yüklenemiyor. Varsa `ID` değerler eşleşmiyorsa, henüz yüklenmemiş paketi ayrı bir uzantısı olarak tanınır.  
  
 Geliştirme sırasında çakışmaları önlemek için uzantıları sürüyor, önceki sürümlerini kaldırdıktan ve ayrıca kaldırın veya diğer potansiyel olarak çakışan uzantılarını devre dışı öneririz.  
  
### <a name="to-update-an-extension-on-your-system"></a>Uzantı, sisteminizdeki güncelleştirmek için  
  
1.  Üzerinde **Araçları** menüsünde tıklatın **Uzantılar ve güncelleştirmeler**.  
  
2.  Sol bölmede **güncelleştirmeleri**.  
  
3.  Orta bölmede, yüklemek istediğiniz Güncelleştir'i tıklatın.  
  
     Güncelleştirilmiş uzantısı sürüm numarasını sağ bölmede, diğer bilgileriyle birlikte görüntülenir.  
  
4.  Sağ bölmede altında tıklatın **güncelleştirme**.  
  
### <a name="to-publish-an-update-of-an-extension"></a>Bir güncelleştirme bir uzantısı yayımlamak için  
  
1.  Visual Studio'da Çözüm güncelleştirmek istediğiniz uzantısı için açın. Değişiklikleri yapın.  
  
    > [!IMPORTANT]
    >  İmzasız tüm kullanıcı uzantıları otomatik olarak güncelleştirilmesi değil. Her zaman uzantılarınızın imzalamanız gerekir.  
  
2.  İçinde **Çözüm Gezgini**, source.extension.manifest açın.  
  
3.  Bildirim Tasarımcısı'nda sayısı değerini artırın **sürüm** alan.  
  
4.  Çözüm kaydedin ve bu derleme.  
  
5.  Yeni .vsix dosyası (Proje \bin\Debug\ klasöründe) karşıya [Visual Studio Market'te](https://marketplace.visualstudio.com/vs) Web sitesi.  
  
     Uzantısı'nın önceki bir sürümü olan bir kullanıcı açıldığında **Uzantılar ve güncelleştirmeler**, yeni sürümü görünür **güncelleştirmeleri** aracı güncelleştirme otomatik olarak aramak için ayarlanmış olması koşuluyla, liste.  
  
     Etkinleştirmek veya alt kısmındaki güncelleştirmeleri için otomatik denetimini devre dışı bırakmak **güncelleştirmeleri** bölmesinde (**etkinleştir/devre dışı bırak kullanılabilir güncelleştirmeleri otomatik olarak algılanmasını**), hangi değişikliklerin **denetle güncelleştirmeleri** ayarı **Araçlar / Seçenekler / ortamı / Uzantılar ve güncelleştirmeler**.  
  
    > [!NOTE]
    >  Visual Studio 2015 güncelleştirme 2'de başlayarak, belirtebilirsiniz (içinde **Araçlar / Seçenekler / ortamı / Uzantılar ve güncelleştirmeler**) kullanıcı başına uzantılar, tüm kullanıcı uzantıları veya her iki (varsayılan ayar) için Otomatik Güncelleştirmeler isteyip istemediğinizi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSIX paketi anatomisi](../extensibility/anatomy-of-a-vsix-package.md)   
 [Visual Studio Uzantıları’nı bulma ve kullanma](../ide/finding-and-using-visual-studio-extensions.md)
