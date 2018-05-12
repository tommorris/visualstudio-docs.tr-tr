---
title: Başlat | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: b85d0fe9-f67a-4b7c-8d48-7eecf3f2dfe9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0b9c699056a3ef4ee493397e99e37f41cbd2cf3e
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="start"></a>Başlat
**Başlat** belirtilen profil oluşturma yöntemi için profil oluşturucu başlatır VSPerfCmd.exe seçeneği bir seçenektir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cmd  
VSPerfCmd.exe /Start:Method /Output:FileName [Options]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Method`  
 Aşağıdaki anahtar sözcüklerden biri olmalıdır:  
  
-   **İzleme** -izleme yöntemini belirtir.  
  
-   **ÖRNEK** -örnekleme yöntemini belirtir.  
  
-   **KAPSAMI** -kod kapsamı belirtir.  
  
-   **EŞZAMANLILIK** -kaynak çakışması yöntemini belirtir.  
  
## <a name="required-options"></a>Gerekli seçenekler  
 **Çıkış** seçeneği olmalıdır belirtilen **Başlat** komut satırında belirtilen.  
  
 **Çıktı:** `filename`  
 Çıktı dosyası adını belirtir.  
  
## <a name="exclusive-options"></a>Dışlayan seçenekleri  
 Aşağıdaki seçenekler yalnızca kullanılabilir **Başlat** bir komut satırı seçeneği.  
  
 **CrossSession**&#124;**CS**  
 Etkinleştirir çapraz profil işlem. Seçenek adları **CrossSession** ve **CS** desteklenen olan iki.  
  
 **Kullanıcı:**[`domain\`]`username`  
 İstemci erişimi için İzleyici belirtilen hesabından sağlar.  
  
 **WinCounter:** `Path` [**otomatik işaret**:`n`]  
 **WinCounter** profil oluşturma veri dosyasındaki bir işareti olarak eklemek için bir Windows performans sayacı belirtir. **Otomatik işaret** veri dosyasının koleksiyonları arasında milisaniye cinsinden zaman aralığını belirtir.  
  
## <a name="invalid-options"></a>Geçersiz seçenekleri  
 Aşağıdaki seçenekler kullanılamaz **Başlat** bir komut satırı seçeneği.  
  
 **Status**  
 **Durum** profili bu işlemleri için geçerlidir. İşlemler ve iş parçacıkları ve geçerli profil durumlarına (açık/kapalı) listeler. Örneğin, bir işlem durursa, **durum** Bu raporda belirtmez. **Durum** işlemi ya da veya profili olduğunu gösterir.  
  
 **Kapatma**[**:**`Timeout`]  
 Profil Oluşturucu kapatır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek VSPerfCmd.exe kullanımı gösterilmiştir **Başlat** seçeneği profil oluşturucu başlatılamadı.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)