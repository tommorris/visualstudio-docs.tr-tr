---
title: '&lt;Dağıtım&gt; öğesi (ClickOnce dağıtımı) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#subscription
- urn:schemas-microsoft-com:asm.v2#beforeApplicationStartup
- urn:schemas-microsoft-com:asm.v2#deploymentProvider
- urn:schemas-microsoft-com:asm.v2#update
- urn:schemas-microsoft-com:asm.v2#deployment
- urn:schemas-microsoft-com:asm.v2#expiration
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <deployment> element [ClickOnce deployment manifest]
ms.assetid: 4fafa9c2-97a0-4cea-b8fd-9746dca33af4
caps.latest.revision: 30
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 0caff13f84208152b3fa2ff4e56a7a2c7f0b6dd7
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="ltdeploymentgt-element-clickonce-deployment"></a>&lt;Dağıtım&gt; öğesi (ClickOnce dağıtımı)
Güncelleştirmeleri ve sistem maruz dağıtımı için kullanılan öznitelikleri tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      <deployment   
   install  
   minimumRequiredVersion  
   mapFileExtensions  
   disallowUrlActivation  
   trustUrlParameters  
>   
   <subscription>   
         <update>   
            <beforeApplicationStartup/>   
            <expiration  
               maximumAge  
               unit  
            />  
         </update>    
   </subscription>   
   <deploymentProvider   
      codebase   
   />   
</deployment>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `deployment` Öğesi gereklidir ve yer `urn:schemas-microsoft-com:asm.v1` ad alanı. Öğesi aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`install`|Gerekli. Bu uygulamayı Windows bulunmayı tanımlar olup olmadığını belirtir **Başlat** menü ve Denetim Masası'nda **Program Ekle veya Kaldır** uygulama. Geçerli değerler `true` ve `false`. Varsa `false`, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ağdan bu uygulamanın en son sürümü her zaman çalışacağını ve değil algılar `subscription` öğesi.|  
|`minimumRequiredVersion`|İsteğe bağlı. İstemci üzerinde çalışan bu uygulamanın en düşük sürümü belirtir. Uygulamanın sürüm numarasını dağıtım bildiriminde sağlanan sürüm numarasından daha az ise, uygulama çalışmaz. Sürüm numaraları biçiminde belirtilmelidir `N.N.N.N`, burada `N` işaretsiz tamsayıdır. Varsa `install` özniteliği `false`, `minimumRequiredVersion` ayarlanmamalıdır.|  
|`mapFileExtensions`|İsteğe bağlı. Varsayılan olarak `false`. Varsa `true`, Dağıtımdaki tüm dosyalar .deploy uzantısına sahip olmalıdır. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bunları Web sunucusundan indirir hemen sonra bu uzantıyı bu dosyalardan çıkarır. Kullanarak uygulamanızı yayımlarsanız [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], otomatik olarak tüm dosyalara bu uzantıyı ekler. Bu parametre tüm dosyaların veren bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] .exe gibi "güvenli olmayan" uzantılarla bitiş dosyaların aktarımını engelleyen bir Web sunucusundan yüklenecek dağıtım.|  
|`disallowUrlActivation`|İsteğe bağlı. Varsayılan olarak `false`. Varsa `true`, yüklü bir uygulama URL'ye tıklayarak veya Internet Explorer'a URL'yi girerek başlatılmasını engeller. Varsa `install` özniteliği mevcut değil, bu öznitelik dikkate alınmaz.|  
|`trustURLParameters`|İsteğe bağlı. Varsayılan olarak `false`. Varsa `true`, URL'nin uygulamaya geçirilen sorgu dizesi parametreleri içermesine izin verir, çok gibi komut satırı bağımsız değişkenleri için komut satırı uygulaması geçirilir. Daha fazla bilgi için bkz: [nasıl yapılır: çevrimiçi bir ClickOnce uygulamasında sorgu dize bilgilerini alma](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md).<br /><br /> Varsa `disallowUrlActivation` özniteliği `true`, `trustUrlParameters` bildirimden hariç, veya açıkça ayarlamak `false`.|  
  
 `deployment` Öğesi de aşağıdaki alt öğeleri içerir.  
  
## <a name="subscription"></a>Abonelik  
 İsteğe bağlı. İçeren `update` öğesi. `subscription` Öğesi özniteliklere sahip değildir. Varsa `subscription` öğesi yok, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama hiçbir zaman güncelleştirmeleri için tarama. Varsa `install` özniteliği `deployment` öğesi `false`, `subscription` öğesi göz ardı edilir, çünkü bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ağdan başlatılan her zaman uygulamanın son sürümü kullanır.  
  
## <a name="update"></a>Güncelleştirme  
 Gerekli. Bu öğe bir alt öğesi değil `subscription` öğesi ve ya da içeren `beforeApplicationStartup` veya `expiration` öğesi. `beforeApplicationStartup` ve `expiration` hem de aynı dağıtım bildiriminde belirtilemez.  
  
 `update` Öğesi özniteliklere sahip değildir.  
  
## <a name="beforeapplicationstartup"></a>beforeApplicationStartup  
 İsteğe bağlı. Bu öğe bir alt öğesi değil `update` öğesi ve özniteliklere sahiptir. Zaman `beforeApplicationStartup` öğesi var, uygulama olacak ne zaman engellenen [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] güncelleştirmeleri, istemcinin çevrimiçi olup olmadığını denetler. Bu öğe yoksa [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ilk için belirtilen değerlere dayalı güncelleştirmeleri için tarama yapmadan `expiration` öğesi. `beforeApplicationStartup` ve `expiration` hem de aynı dağıtım bildiriminde belirtilemez.  
  
## <a name="expiration"></a>süre sonu  
 İsteğe bağlı. Bu öğe bir alt öğesi değil `update` öğesi ve alt öğesi yok. `beforeApplicationStartup` ve `expiration` hem de aynı dağıtım bildiriminde belirtilemez. Mevcut sürümü çalışırken güncelleştirme denetimi oluşur ve güncel bir sürüm algılandı, yeni sürüm önbelleğe alınır. Üzerinde sonraki başlatın ardından yeni sürümü yükler [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.  
  
 `expiration` Öğesi aşağıdaki öznitelikleri destekler.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`maximumAge`|Gerekli. Uygulama güncelleştirme denetimi gerçekleştirmeden önce geçerli güncelleştirmesi ne kadar eski olması gerektiğini tanımlar. Zaman birimi tarafından belirlenen `unit` özniteliği.|  
|`unit`|Gerekli. İçin zaman birimi tanımlar `maximumAge`. Geçerli birimleridir `hours`, `days`, ve `weeks`.|  
  
## <a name="deploymentprovider"></a>deploymentProvider  
 .NET Framework 2.0 için dağıtım bildirimi içeriyorsa, bu öğe gereklidir bir `subscription` bölümü. .NET Framework 3.5 ve daha sonra bu öğe isteğe bağlıdır ve dağıtım bildirimi bulunan dosya yolu ve sunucu için varsayılan olur.  
  
 Bu öğe bir alt öğesi değil `deployment` öğesi ve aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`codebase`|Gerekli. Konum, Tekdüzen Kaynak Tanımlayıcısı (URI) olarak güncelleştirmek için kullanılan dağıtım bildiriminin tanımlar [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama. Bu öğe, CD tabanlı yüklemeler için güncelleştirme konumlarını iletmek için de sağlar. Geçerli bir URI olmalıdır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yapılandırabileceğiniz, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] başlangıçta, güncelleştirmeleri taramak için uygulama başlatma işleminden sonra güncelleştirmeleri için tarama veya hiçbir zaman Güncelleştirmeleri denetle. Başlangıçta güncelleştirmeleri taramak için emin `beforeApplicationStartup` öğesi var. altında `update` öğesi. Başlatma işleminden sonra güncelleştirmeleri taramak için emin `expiration` öğesi var. altında `update` öğesi ve güncelleştirme aralıkları sağlanır.  
  
 Güncelleştirmeleri denetleme devre dışı bırakmak için kaldırmak `subscription` öğesi. Hiçbir zaman güncelleştirmeleri taramak için dağıtım bildiriminde belirttiğinizde, yine de el ile güncelleştirmeleri kullanarak denetleyebilirsiniz <xref:System.Deployment.Application.ApplicationDeployment.CheckForUpdate%2A> yöntemi.  
  
 DeploymentProvider'ın güncelleştirmeleri nasıl olduğu hakkında daha fazla bilgi için bkz: [ClickOnce güncelleştirme stratejisini seçme](../deployment/choosing-a-clickonce-update-strategy.md).  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki kod örneği gösterilmektedir bir `deployment` öğesinde bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım bildirimi. Örnek kullanan bir `deploymentProvider` tercih edilen güncelleştirme konumunu göstermek için öğesi.  
  
```  
<deployment install="true" minimumRequiredVersion="2.0.0.0" mapFileExtension="true" trustUrlParameters="true">  
    <subscription>  
      <update>  
        <expiration maximumAge="6" unit="hours" />  
      </update>  
    </subscription>  
    <deploymentProvider codebase="http://www.adatum.com/MyApplication.application" />  
  </deployment>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Dağıtım Bildirimi](../deployment/clickonce-deployment-manifest.md)