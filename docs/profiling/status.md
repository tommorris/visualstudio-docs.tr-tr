---
title: Durum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ba656fa4-ef9d-4d8c-a3b6-739c3b5d23ae
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3611b7a352028babc28cecef2c04753e44d9796e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="status"></a>Durum
VSPerfCmd.exe **durum** seçeneği profil oluşturucu ve şu anda profili oluşturuluyor herhangi bir işlem durumuyla ilgili bilgileri görüntüler.  
  
 **Durum** seçeneği, komut satırında belirtilen tek seçenek olmalıdır. Profil Oluşturucu ile VSPerfCmd.exe başlatılmalıdır **Başlat** herhangi bir durumla görüntülenebilmesi seçeneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
VSPerfCmd.exe /Status  
```  
  
#### <a name="parameters"></a>Parametreler  
 Yok.  
  
## <a name="remarks"></a>Açıklamalar  
 **Durum** seçenek profil oluşturucu için aşağıdaki durum bilgileri görüntüler.  
  
 **Çıktı dosyası adı**  
 Geçerli profil oluşturucu veri dosyası yolu ve dosya adı.  
  
 **Koleksiyon modu**  
 Örnek veya izleme  
  
 **En fazla işlemleri**  
 Bir kerede profili işlemleri maksimum sayısı ve şu anda etkin işlemlerin sayısı.  
  
 **Maksimum iş parçacıkları**  
 Bir kerede profili iş parçacığı sayısı.  
  
 **Arabellek sayısı**  
 Profil oluşturma veri yazmada ayrılmış bellek arabellek sayısı.  
  
 **Arabellek boyutu**  
 Bellek arabellek, bayt cinsinden boyutu.  
  
 **Durum** seçenek şu anda profili oluşturuluyor her işlem için aşağıdaki durum bilgileri görüntüler.  
  
 **İşlem**  
 Profili işlemin adı.  
  
 **İşlem kimliği**  
 İşlem sistem tanımlayıcısı.  
  
 **NUM iş parçacıkları**  
 Şu anda yürütülmekte olan iş parçacığı sayısı.  
  
 **Count Başlat/Durdur**  
 Bu işlem için veri toplama denetlemek için birincil iç Profil Oluşturucu sayısı. Sayı verileri toplamak için birine eşit olmalıdır. Profil Oluşturucu API'ler ve VSPerfCmd seçenekleri tarafından Başlat/Durdur sayısı değişebilir **GlobalOn**, **GlobalOff**, **ProcessOn**, **ProcessOff**, **ThreadOn**, ve **ThreadOff**.  
  
 **Count askıya/Sürdür**  
 Bu işlem için veri toplama denetlemek için ikincil iç Profil Oluşturucu sayısı. Sayısı verileri toplamak için sıfıra eşit veya daha az olmalıdır. **Askıya alma/sürdürmeden** sayısı yalnızca profil oluşturucu tarafından API'leri yönetilebilir.  
  
 **İzlemek için erişim haklarına sahip kullanıcılar**  
 Profil Oluşturucu erişebilen kullanıcıları adlarını listeler. Ek kullanıcılar olanağı verilir erişim VSPerfCmd.exe kullanarak **yönetici** seçeneği  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil oluşturma hizmetleri](../profiling/command-line-profiling-of-services.md)