---
title: "ClickOnce yönetilmeyen API Başvurusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- LaunchApplication [ClickOnce unmanaged]
- ClickOnce, unmanaged APIs
- CleanOnlineAppCache [ClickOnce unmanaged]
- CleanOnlineAppCacheW interface [ClickOnce unmanaged]
- GetDeploymentDataFromManifest [ClickOnce unmanaged]
ms.assetid: ec002138-4054-456d-bcc1-79ac2f4a4fd7
caps.latest.revision: "6"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 11e10800ff51abd6f95447d85204a44f8367f551
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="clickonce-unmanaged-api-reference"></a>ClickOnce Yönetilmeyen API Başvurusu
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]dfshim.DLL'den yönetilmeyen ortak API'leri.  
  
## <a name="cleanonlineappcache"></a>CleanOnlineAppCache  
 Temizler ve tüm çevrimiçi uygulamaları kaldırır [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama önbelleği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde hata temsil eden bir HRESULT döndürür. Yönetilen bir özel durum oluşursa, 0x80020009 (DISP_E_EXCEPTION) döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 CleanOnlineAppCache çağırma başlayacak [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] zaten çalışmıyorsa, hizmet.  
  
## <a name="getdeploymentdatafrommanifest"></a>GetDeploymentDataFromManifest  
 Dağıtım bilgileri bildirim ve etkinleştirme URL'den alır.  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|Tür|  
|---------------|-----------------|----------|  
|`pcwzActivationUrl`|Bir işaretçi `ActivationURL`.|LPCWSTR|  
|`pcwzPathToDeploymentManifest`|Bir işaretçi `PathToDeploymentManifest`.|LPCWSTR|  
|`pwzApplicationIdentity`|Bir işaretçi tam uygulama kimliğini belirten NULL ile sonlandırılmış bir dize almak üzere arabellek.|LPWSTR|  
|`pdwIdentityBufferLength`|Bir işaretçi uzunluğu olan DWORD `pwzApplicationIdentity` arabelleğinin WCHAR'lar içinde. Bu alanı boş sonlandırma karakter içerir.|LPDWORD|  
|`pwzProcessorArchitecture`|Uygulama dağıtımı, bildirimindeki işlemci mimarisini belirten NULL ile sonlandırılmış bir dize almak üzere arabellek için bir işaretçi.|LPWSTR|  
|`pdwArchitectureBufferLength`|Bir işaretçi uzunluğu olan DWORD `pwzProcessorArchitecture` arabelleğinin WCHAR'lar içinde.|LPDWORD|  
|`pwzApplicationManifestCodebase`|Bildirimden uygulama bildiriminin codebase belirten NULL ile sonlandırılmış bir dize almak üzere arabellek için bir işaretçi.|LPWSTR|  
|`pdwCodebaseBufferLength`|Bir işaretçi uzunluğu olan DWORD `pwzApplicationManifestCodebase` arabelleğinin WCHAR'lar içinde.|LPDWORD|  
|`pwzDeploymentProvider`|Sonlandırılmış bir dize almak üzere bir arabellek için bir işaretçi varsa bildirimden dağıtım sağlayıcıyı belirtir. Aksi takdirde, boş bir dize döndürülür.|LPWSTR|  
|`pdwProviderBufferLength`|Bir işaretçi uzunluğu olan DWORD `pwzProviderBufferLength`.|LPDWORD|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde hata temsil eden bir HRESULT döndürür. Arabellek çok küçük ise HRESULTFROMWIN32(ERROR_INSUFFICIENT_BUFFER) döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretçiler null olmamalıdır. `pcwzActivationUrl`ve `pcwzPathToDeploymentManifest` boş olmamalıdır.  
  
 Etkinleştirme URL'sini temizlemek yapanın sorumluluğundadır. Örneğin, kaçış eklenmesi gereken yerlere veya sorgu dizesini kaldırma karakter.  
  
 Giriş uzunluğunu sınırlamak yapanın sorumluluğundadır. Örneğin, URL uzunluğu üst sınırı 2 KB'tır.  
  
## <a name="launchapplication"></a>LaunchApplication  
 Başlatır veya bir dağıtım URL'yi kullanarak bir uygulamayı yükler.  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|Tür|  
|---------------|-----------------|----------|  
|`deploymentUrl`|Dağıtım bildirimi URL'sini içeren NULL ile sonlandırılmış bir dize için bir işaretçi.|LPCWSTR|  
|`data`|Daha sonraki kullanımlar için ayrılmıştır. NULL olmamalıdır.|LPVOID|  
|`flags`|Daha sonraki kullanımlar için ayrılmıştır. 0 olmalıdır.|DWORD|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, S_OK verir; Aksi takdirde hata temsil eden bir HRESULT döndürür. Yönetilen bir özel durum oluşursa, 0x80020009 (DISP_E_EXCEPTION) döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Deployment.Application.DeploymentServiceCom.CleanOnlineAppCache%2A>