---
title: 'Nasıl yapılır: Visual Studio çözümünün parçası olmayan bir yürütülebilir dosyada hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], executables
- executable files, importing
- executable files, debugging outside of projects
ms.assetid: 3ea176e8-1ce5-42c4-b7a2-abe3a2765033
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ce84c4acdc2cf4324c76dbbf7fe0b39ca9715b3c
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279108"
---
# <a name="how-to-debug-an-executable-that-is-not-part-of-a-visual-studio-solution"></a>Nasıl yapılır: Visual Studio çözümünün parçası olmayan bir yürütülebilir dosyada hata ayıklama
Bazen, hata ayıklama olmayan bir yürütülebilir (.exe dosyası) isteyebilirsiniz parçası olan bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje. Oluşturduğunuz dışında bir yürütülebilir dosya olabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ya da başka birinden aldığınız bir çalıştırılabilir.  
  
Visual Studio dışında yürütülebilir dosyayı başlatmak ve onu kullanarak eklemek için bu sorunun her zamanki yanıtı olan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata ayıklayıcı. Daha fazla bilgi için [çalışan işlemlere ekleme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
Bir uygulamaya eklemek, birkaç saniye sürer, bazı adımları el ile gerektirir. Bu gecikme, başlatma sırasında oluşan bir sorunu çözmeye çalışıyorsanız, eklemenin yardımcı olmayacağı olduğunu gösterir. Ayrıca, kullanıcı girişini beklemeyen ve hızlı şekilde biten bir program ayıklıyorsanız, buna eklemek için zaman olmayabilir. Varsa [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] ve [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] yüklü, böyle bir program için EXE projesi oluşturabilirsiniz.

> [!NOTE]
>  Programlama dillerinin tümü EXE projelerini desteklemez.

Visual Studio çözümünün parçası olmayan yürütülebilir bir dosya ayıklanırken çalışan yürütülebilir bir ekleme ya da yürütülebilir dosyasına ekleyin kullanılabilir hata ayıklama özellikleri sınırlı olabilir bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözüm.

- Kaynak kodu varsa, kaynak koda içeri aktarmak için en iyi yaklaşım olan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve yürütülebilir dosya hata ayıklama yapısını oluşturmak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].
- Kaynak kodu yoksa ve çalıştırılabilir olmadan oluşturulduysa [hata ayıklama bilgileri](../debugger/how-to-set-debug-and-release-configurations.md) uyumlu bir biçimde kullanılabilir hata ayıklama özellikleri çok sınırlıdır. 
  
### <a name="to-create-an-exe-project-for-an-existing-executable"></a>Varolan bir yürütülebilir dosya için bir EXE projesi oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde tıklatın **açık** seçip **proje**.  
  
2.  İçinde **Proje Aç** iletişim kutusu, açılan listeyi tıklatın **dosya adı** kutusunda ve seçin **tüm proje dosyaları**.  
  
3.  Yürütülebilir dosyayı bulun ve tıklatın **Tamam**.  

    Bu yürütülebilir dosya içeren geçici bir çözüm oluşturur.

5.  Yürütülebilir bir yürütme komutu seçerek Başlat **Başlat**, gelen **hata ayıklama** menüsü.    
  
### <a name="to-import-an-executable-into-a-visual-studio-solution"></a>Bir yürütülebilir dosya bir Visual Studio çözümüne aktarmak için  
  
1.  Üzerinde **dosya** menüsünde **Proje Ekle**ve ardından **mevcut proje**.  
  
2.  İçinde **Varolan Proje Ekle** iletişim kutusu, açılan listeyi tıklatın **dosya adı** kutusunda ve seçin **tüm proje dosyaları**.  
  
3.  Bulup yürütülebilir dosyayı seçin.  
  
4.  **Tamam**'ı tıklatın.  
  
5.  Yürütülebilir bir yürütme komutu seçerek Başlat **Başlat**, gelen **hata ayıklama** menüsü.    
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)   
 [Hata ayıklayıcısı güvenliği](../debugger/debugger-security.md)   
 [DBG dosyaları](/previous-versions/visualstudio/visual-studio-2010/da528y14(v=vs.100))