---
title: "SccHistory işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccHistory
helpviewer_keywords: SccHistory function
ms.assetid: a636d9d3-47c1-4b48-ac6b-bcfde19d6cf9
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 93c32d9eaa3549529a649472550ec8268cd0f6e5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="scchistory-function"></a>SccHistory işlevi
Bu işlev, belirtilen dosyaları geçmişini görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccHistory(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pvContext`  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 `hWnd`  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 `nFiles`  
 [in] Belirtilen dosya sayısı `lpFileName` dizi.  
  
 `lpFileName`  
 [in] Dosyaların tam olarak nitelenmiş adlar dizisi.  
  
 `fOptions`  
 [in] Komutunu bayrakları (şu anda kullanılmaz).  
  
 `pvOptions`  
 [in] Kaynak denetimi fişi özel seçenekleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Sürüm Geçmişi başarıyla alındı.|  
|SCC_I_RELOADFILE|Diskteki dosya gerçekten değişiklik geçmişini getirilirken (örneğin, eski bir sürümü alarak), kaynak denetim sistemi IDE bu dosyayı yeniden şekilde.|  
|SCC_E_FILENOTCONTROLLED|Dosya kaynak denetimi altında değil.|  
|SCC_E_OPNOTSUPPORTED|Kaynak Denetim sistem bu işlemi desteklemiyor.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi gerçekleştirmek için izin verilmiyor.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu. Yeniden deneme önerilir.|  
|SCC_E_PROJNOTOPEN|Proje değiştirilmediğinden açılır.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata oluştu. Dosya geçmişi alınamadı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kaynak Denetim eklentisi her dosya geçmişini görüntülemek için kendi iletişim kutusundaki görüntüleyebilirsiniz kullanarak `hWnd` üst pencere olarak. Alternatif olarak, isteğe bağlı geri çağırma çıktıyı işlevi sağlanan için [SccOpenProject](../extensibility/sccopenproject-function.md) onu destekleniyorsa, kullanılabilir.  
  
 Belirli koşullar altında bu çağrıyı yürütülmesi sırasında incelenmesi dosyayı değiştirmek olduğunu unutmayın. Örneğin, [!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] geçmişi komutu kullanıcı dosyanın eski bir sürümünü almak için bir fırsat sunar. Böyle bir durumda, kaynak denetim eklentisi döndürür `SCC_I_RELOAD` dosyayı yeniden yüklemeniz gerektiğini IDE uyarmak için.  
  
> [!NOTE]
>  Kaynak Denetim eklentisi dosyaları dizisi için bu işlevi desteklemiyorsa, yalnızca ilk dosya için dosya geçmişi görüntülenebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)