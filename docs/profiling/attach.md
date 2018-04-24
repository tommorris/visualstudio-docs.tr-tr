---
title: Ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 79614283-6733-4592-a53a-d428052271ad
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 98e18456ad4665359e33d7a9b5f064585f8195be
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="attach"></a>İliştir
VSPerfCmd.exe **Attach** seçeneği başlar çalışan işleminin işlem kimliği (PID) tarafından belirtilen örnek profil.  
  
 Kullanılacak **Attach** seçeneğini belirtmelisiniz **örnek** başlangıç seçeneği yöntemi.  
  
> [!NOTE]
>  Varsa **Başlat** seçeneği ile belirtilen **Crosssession** seçeneğini yapılan her çağrı **VSPerfCmd /Attach** veya **VSPerfCmd /Detach** gerekir Ayrıca belirtin **Crosssession**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Attach:ProcessID [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ProcessID`  
 İşlem kimliği (PID) çalışan işlemi. Çalışan bir işlemi PID Windows Görev Yöneticisi'nin İşlemler sekmesinde listelenir.  
  
## <a name="valid-options"></a>Geçerli seçenekleri  
 Aşağıdaki **VSPerfCmd** seçenekleri ile birleştirilebilir **Attach** tek bir komut satırı seçeneği.  
  
 **Crosssession**  
 Oturumlarında oturum dışında profil oluşturma uygulamaları etkinleştirir. Gerekli olursa **Başlat** seçeneği ile belirtilen **Crosssession** seçeneği.  
  
 **Başlat:** `Method`  
 Komut satırı Profil Oluşturucu oturumu başlatır ve belirtilen profil oluşturma yöntemini ayarlar.  
  
 **TargetCLR**  
 Profil oluşturma oturumu içinde birden fazla sürümü yüklendiğinde, .NET Framework ortak dil çalışma zamanı (CLR) profiline sürümünü belirtir. Varsayılan olarak, ilk yüklenen sürüm profili.  
  
 **GlobalOn GlobalOff**  
 Sürdürür (**GlobalOn**) veya duraklatır (**GlobalOff**) profil, ancak profil oluşturma oturumu bitmez.  
  
 **ProcessOn:** `PID` **ProcessOff:** `PID`  
 Sürdürür (**ProcessOn**) veya duraklatır (**ProcessOff**) belirtilen işlem için profil oluşturma.  
  
## <a name="interval-options"></a>Aralık Seçenekleri  
 Örnekleme aralığı şunlardan birini Attach komut satırında belirtilebilir. Varsayılan örnekleme aralığı 10,000,000 işlemci saat döngüsü ' dir.  
  
 **Zamanlayıcı**[**:**`Cycles`]**PF**[**:**`Events`]**Sys**[**:** Olayları]**sayaç**[**:**`Name`,`Reload`,`FriendlyName`]  
 Örnekleme aralığı türü ve numarası belirtir.  
  
-   **Zamanlayıcı** -Samples her `Cycles` işlemci saat döngüsü. Varsa `Cycles` belirtilmezse, 10,000,000 döngüleri kullanılır.  
  
-   **PF** -Samples her `Events` sayfa hataları. Varsa `Events` belirtilmezse, 10 sayfa hataları kullanılır.  
  
-   **Sys** -Samples her `Events` çağrıları işletim sistemi. Varsa `Events` belirtilmezse, 10 sistem çağrıları kullanılır.  
  
-   **Sayaç** -Samples her `Reload` CPU performans sayacı tarafından belirtilen sayıda `Name`. İsteğe bağlı olarak, `FriendlyName` profil oluşturucu raporlarında sütun başlığı olarak kullanılacak bir dize belirtebilirsiniz.  
  
## <a name="example"></a>Örnek  
 Bu örnek, 12345 işlem kimliği, çalışan bir uygulama örneğini ekleme gösterilmiştir.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Attach:12345  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)