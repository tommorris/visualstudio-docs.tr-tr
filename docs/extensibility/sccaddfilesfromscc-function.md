---
title: "SccAddFilesFromSCC işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccAddFilesFromSCC
helpviewer_keywords: SccAddFilesFromSCC function
ms.assetid: f21a3500-ade8-4dd8-8647-10e2179be9c1
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1764bfc503e25860326b1910c432edcf95c8f21c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sccaddfilesfromscc-function"></a>SccAddFilesFromSCC işlevi
Bu işlev dosyaların listesini kaynak denetiminden açık projeye ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccAddFilesFromSCC(  
   LPVOID  pContext,  
   HWND    hWnd,  
   LPSTR   lpUser,  
   LPSTR   lpAuxProjPath,  
   LONG    cFiles,  
   LPCSTR* lpFilePaths,  
   LPCSTR  lpDestination,  
   LPCSTR  lpComment,  
   LPBOOL  pbResults  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pContext  
 [in] Kaynak Denetim eklentisi bağlam işaretçi.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 lpUser  
 [içinde out] Kullanıcı adı (kadar SCC_USER_SIZE, null Sonlandırıcı dahil olmak üzere).  
  
 lpAuxProjPath  
 [içinde out] Proje tanımlayan yardımcı dize (en fazla `SCC_PRJPATH_`null Sonlandırıcı dahil BOYUTU).  
  
 cFiles  
 [in] Tarafından verilen dosya sayısı `lpFilePaths`.  
  
 lpFilePaths  
 [içinde out] Geçerli projeye eklemek için dosya adları dizisi.  
  
 lpDestination  
 [in] Yazılacak dosyaların nerede hedef yolu.  
  
 lpComment  
 [in] Eklenmekte olan dosyaların her biri için uygulanacak açıklama.  
  
 pbResults  
 [içinde out] Başarı (sıfır olmayan veya doğru) belirtmek için set ya da hata bayrakları dizisi (sıfır veya FALSE) her dosya için (dizinin boyutu en az olmalıdır `cFiles` uzun).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_E_PROJNOTOPEN|Proje açık değil.|  
|SCC_E_OPNOTPERFORMED|Bağlantı tarafından belirtilen aynı projeye değil`lpAuxProjPath.`|  
|SCC_E_NOTAUTHORIZED|Kullanıcı veritabanını güncelleştirmek için yetkili değil.|  
|SCC_E_NONSPECIFICERROR|Bilinmeyen hata.|  
|SCC_I_RELOADFILE|Bir dosya veya projeyi yeniden yüklenmesi gerekiyor.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)