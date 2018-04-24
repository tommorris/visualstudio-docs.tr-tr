---
title: 'Yönetilen hata ayıklama: Önerilen özellik ayarları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], managed
- debugging managed code, recommended property settings
ms.assetid: 3d14a8d4-2925-44d0-be41-ec546d411db9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: e1c4b725871012f1fbf2c80f3e978f133d4db5b0
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="managed-debugging-recommended-property-settings"></a>Yönetilen Hata Ayıklama: Önerilen Özellik Ayarları
Bazı özellikler tüm yönetilen hata ayıklama senaryoları için aynı şekilde ayarlamanız gerekir.  
  
 Aşağıdaki tablolarda, önerilen özellik ayarları görüntüleyin.  
  
 Burada listelenmeyen ayarları farklı yönetilen proje türleri arasında farklılık gösterebilir. Örneğin, **eylemi Başlat** farklı biçimde bir Windows Forms projesinde ayarlanacak bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] projesi.  
  
### <a name="configuration-properties-on-the-build-c-or-compile-visual-basic-tab"></a>Derleme (C#) veya derleme (Visual Basic) sekmesinde yapılandırma özellikleri  
  
|**Özellik adı**|**Ayarı**|  
|-----------------------|-----------------|  
|**Hata ayıklama sabiti tanımlayın**|C# ve F #: onay kutusunun işaretli olarak ayarlayın. Bu hata ayıklama sınıfı kullanmak için uygulamanızı sağlar.|  
|**İzleme sabiti tanımlayın**|C# ve F #: onay kutusunun işaretli olarak ayarlayın. Bu izleme sınıfını kullanmak uygulamanızı sağlar.|  
|**Kod en iyi duruma getirme**|C#, F # ve Visual Basic: false olarak ayarlayın. Oluşturulan yönergeleri doğrudan kaynak koduna karşılık gelmediğinden en iyi duruma getirilmiş daha zor hata ayıklamak için kodudur. Programınızı sahip yalnızca iyileştirilmiş kodda görüntülenen hata fark ederseniz, bu ayarı etkinleştirmek, ancak gösterilen kodu unutmayın **ayrıştırılmış** penceresi kodda gördükleri eşleşmeyebilir en iyi duruma getirilmiş kaynağından oluşturulur Düzenleyici. İyileştirilmiş kodda hata ayıklama için sadece kendi kodumu etkinleştirmeniz gerekir. (Bkz [sadece kendi kodumu atlama sınırla](../debugger/navigating-through-code-with-the-debugger.md#BKMK_Restrict_stepping_to_Just_My_Code)).<br /><br /> Daha fazla bilgi için bkz: [C# hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-csharp-debug-configurations.md) veya [bir Visual Basic hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-visual-basic-debug-configuration.md).|  
|**Çıkış yolu**|Bin\Debug için ayarlanmış\\.|  
|**Gelişmiş derleme seçenekleri**|Yalnızca Visual Basic. Tıklatın **Gelişmiş** aşağıdaki tabloda açıklanan gelişmiş özelliklerini ayarlamak için.|  
  
### <a name="advanced-compiler-settings-dialog-box"></a>Gelişmiş Derleyici Ayarları iletişim kutusu  
  
|**Özellik adı**|**Ayarı**|  
|-----------------------|-----------------|  
|**En iyi duruma getirme etkinleştir**|Belirtilen nedenlerden dolayı false olarak ayarlanmış **kodu en iyi duruma** önceki tabloda seçeneği.|  
|**Hata ayıklama bilgisi oluştur**|Bu derleme sırasında ayarlanması/Debug bayrağı neden olan hata ayıklama kolaylaştırmak için gereken bilgileri oluşturur kutuyu seçin.|  
|**Hata ayıklama sabiti tanımlayın**|Tanımlamak için bu onay kutusunu işaretleyin `DEBUG` kullanmak için uygulamanızı sağlayan sabiti <xref:System.Diagnostics.Debug> sınıfı.|  
|**İzleme sabiti tanımlayın**|Tanımlamak için bu onay kutusunu işaretleyin `TRACE` kullanmak için uygulamanızı sağlayan sabiti <xref:System.Diagnostics.Trace> sınıfı.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)   
 [C#, F # ve Visual Basic proje türleri](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)