---
title: "SccPopulateList işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccPopulateList
helpviewer_keywords:
- SccPopulateList function
ms.assetid: 7416e781-c571-4a7f-8af3-a089ce8be662
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 474bb834d36661c7cd85b98db78c13f619d7cba6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="sccpopulatelist-function"></a>SccPopulateList işlevi
Bu işlev belirli kaynak denetimi komut için dosyaları listesini güncelleştirir ve kaynak denetimi durumu verilen tüm dosyalarda sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccPopulateList (  
   LPVOID          pvContext,  
   enum SCCCOMMAND nCommand,  
   LONG            nFiles,  
   LPCSTR*         lpFileNames,  
   POPLISTFUNC     pfnPopulate,  
   LPVOID          pvCallerData,  
   LPLONG          lpStatus,  
   LONG            fOptions  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 nKomut  
 [in] Tüm dosyalara uygulanan kaynak denetimi komutu `lpFileNames` dizi (bkz [komut kodu](../extensibility/command-code-enumerator.md) olası komutların listesini görmek için).  
  
 nFiles  
 [in] Dosya sayısı `lpFileNames` dizi.  
  
 lpFileNames  
 [in] Dosya adları IDE bilinen bir dizi.  
  
 pfnPopulate  
 [in] Ekleme ve dosyaları kaldırmak için aramayı IDE geri çağırma işlevi (bkz [POPLISTFUNC](../extensibility/poplistfunc.md) Ayrıntılar için).  
  
 pvCallerData  
 [in] Geri çağırma işlevi değişmeden iletilecek olan değer.  
  
 lpStatus  
 [içinde out] Her dosya için durumu bayrakları döndürmek için eklenti kaynak denetimi için bir dizi.  
  
 fOptions  
 [in] Komut bayrakları ("PopulateList bayrağı" bölümüne bakın [bit işaretleri belirli komutları tarafından kullanılan](../extensibility/bitflags-used-by-specific-commands.md) Ayrıntılar için).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Başarılı.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata oluştu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev, dosyaların listesini görmek için geçerli durumunu inceler. Kullandığı `pfnPopulate` çağıran bir dosya için ölçüt eşleşmediğinde bildirmek için geri çağırma işlevi `nCommand`. Örneğin, komut ise `SCC_COMMAND_CHECKIN` ve listedeki bir dosyayı kullanıma alınmadı sonra geri çağıran bildirmek için kullanılır. Bazen, eklenti kaynak denetimi komutu bir parçası olarak ve bunları Ekle diğer dosyaları bulabilirsiniz. Bu, örneğin, bir Visual Basic kullanıcının bilgilendirilmesine projesi tarafından kullanılan ancak Visual Basic proje dosyasında görünmez bir .bmp dosyası kullanıma izin verir. Kullanıcının seçtiği **almak** IDE'de komutu. IDE kullanıcı alabilirsiniz düşündüğü tüm dosyaların bir listesini görüntüler, ancak liste gösterilen önce `SccPopulateList` işlevi listenin görüntülenecek güncel olduğundan emin olmak için çağrılır.  
  
## <a name="example"></a>Örnek  
 IDE kullanıcı alabilirsiniz düşündüğü dosyaların bir listesini oluşturur. Bu liste görüntülemeden önce çağırır `SccPopulateList` işlev, eklenti kaynak denetimi fırsatı veren ekleyin ve dosyaları listeden silin. Eklenti listesi verilen geri çağırma işlevini çağırarak değiştirir (bkz [POPLISTFUNC](../extensibility/poplistfunc.md) daha fazla ayrıntı için).  
  
 Çağrılacak eklenti devam `pfnPopulate` ekleyen ve tamamlandı ve ardından döndürür kadar dosyalarını siler işlevi `SccPopulateList` işlevi. IDE daha sonra kendi listesini görüntüleyebilirsiniz. `lpStatus` Dizi IDE tarafından geçirilen özgün listesindeki tüm dosyaları temsil eder. Tüm bu dosyaları ayrıca yapma için durumunu eklenti doldurur geri çağırma işlevini kullanın.  
  
> [!NOTE]
>  Kaynak Denetim eklentisi her zaman yalnızca hemen listesi olduğu gibi bırakarak bu işlevden döndürülecek seçeneği vardır. Bir eklenti bu işlevi uyguluyorsa, bu ayarlayarak gösterebilir `SCC_CAP_POPULATELIST` yapılan ilk çağrıda yetenek bit bayrak [SccInitialize](../extensibility/sccinitialize-function.md). Varsayılan olarak, eklenti her zaman geçirilen tüm öğeleri dosyaları varsayılmaktadır. Ancak, IDE ayarlarsa `SCC_PL_DIR` içinde bayrak `fOptions` parametresi, geçirilen tüm öğeleri olan dizinler olarak kabul edilmesi için. Eklenti ait tüm dosyaları dizinler eklemeniz gerekir. IDE hiçbir zaman karışımını dosyaları ve dizinleri geçer.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)   
 [POPLISTFUNC](../extensibility/poplistfunc.md)   
 [Özel komutlar tarafından kullanılan bit işaretleri](../extensibility/bitflags-used-by-specific-commands.md)   
 [Komut kodu](../extensibility/command-code-enumerator.md)