---
title: 'Nasıl yapılır: Visual Studio çözümünün parçası olmayan bir yürütülebilir dosyada hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: d73b122bf882ee1ccf7ce7e35e8a36cd91f2eb07
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-debug-an-executable-that-is-not-part-of-a-visual-studio-solution"></a>Nasıl yapılır: Visual Studio çözümünün parçası olmayan bir yürütülebilir dosyada hata ayıklama
Bazı durumlarda, olmayan bir yürütülebilir dosya (.exe dosyası) hata ayıklama isteyebilirsiniz parçası bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projesi. Dışında oluşturulan bir yürütülebilir dosya olabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] veya başka bir kişiden aldığınız yürütülebilir.  
  
Bu sorun için her zamanki yanıt yürütülebilir Visual Studio dışında başlatmak ve ile ekleme kullanmaktır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata ayıklayıcı. Daha fazla bilgi için bkz: [eklemek için çalışan işlemler](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
Bir uygulamaya eklemek için birkaç saniye sürer için bazı adımları el ile gerekir. Bu gecikme, başlatma sırasında ortaya çıkan bir sorun hata ayıklamak çalışıyorsanız ekleme yardımcı olmayacaktır olduğunu anlamına gelir. Ayrıca, kullanıcı girişi beklemez ve hızlı bir şekilde tamamlandıktan bir program hata ayıklama, kendisine eklemek için zaman olmayabilir. Varsa [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] ve [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] yüklü, böyle bir program için bir EXE proje oluşturabilirsiniz.

> [!NOTE]
>  EXE projeleri tüm programlama dillerini destekler.

Visual Studio çözümünün parçası olmayan bir yürütülebilir dosya ayıklarken yürütülebilir çalışması için bir ekleme ya da yürütülebilir dosyaya ekleyin kullanılabilir hata ayıklama özellikleri sınırlı olabilir bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözümü.

- Kaynak kodu varsa kaynak kodu içine aktarmak için en iyi yaklaşımı olan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve yürütülebilir dosya, hata ayıklama derlemesi oluşturma [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].
- Kaynak kodu yoksa ve yürütülebilir olmadan oluşturuldu [hata ayıklama bilgilerini](../debugger/how-to-set-debug-and-release-configurations.md) uyumlu bir biçimde kullanılabilir hata ayıklama özellikleri çok sınırlıdır. 
  
### <a name="to-create-an-exe-project-for-an-existing-executable"></a>Varolan bir yürütülebilir dosya için bir EXE projesi oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde tıklatın **açık** seçip **proje**.  
  
2.  İçinde **Proje Aç** iletişim kutusunda, aşağı açılan listeden sonraki tıklatın **dosya adı** kutusunda ve seçin **tüm proje dosyalarını**.  
  
3.  Yürütülebilir dosya bulun ve tıklatın **Tamam**.  

    Bu yürütülebilir dosya içeren geçici bir çözüm oluşturur.

5.  Yürütülebilir dosya gibi bir yürütme komutu seçerek Başlat **Başlat**, gelen **hata ayıklama** menüsü.    
  
### <a name="to-import-an-executable-into-a-visual-studio-solution"></a>Visual Studio çözümü yürütülebilir bir dosya aktarmak için  
  
1.  Üzerinde **dosya** menüsündeki **Proje Ekle**ve ardından **mevcut proje**.  
  
2.  İçinde **Varolan Proje Ekle** iletişim kutusunda, aşağı açılan listeden sonraki tıklatın **dosya adı** kutusunda ve seçin **tüm proje dosyalarını**.  
  
3.  Bulun ve yürütülebilir dosya seçin.  
  
4.  **Tamam**'ı tıklatın.  
  
5.  Yürütülebilir dosya gibi bir yürütme komutu seçerek Başlat **Başlat**, gelen **hata ayıklama** menüsü.    
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)   
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [DBG dosyaları](http://msdn.microsoft.com/en-us/91e449e9-8b65-4123-960f-2107cd1f1cfd)