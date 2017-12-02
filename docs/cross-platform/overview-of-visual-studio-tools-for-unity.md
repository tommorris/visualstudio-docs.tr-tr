---
title: "Unity için Visual Studio araçlarına genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4231bb9-45c4-4c77-ac3c-d05033b26393
caps.latest.revision: "4"
author: conceptdev
ms.author: crdun
manager: crdun
ms.openlocfilehash: 2af38cbebc1695a78a86d80240acc40c5463cbed
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/29/2017
---
# <a name="overview-of-visual-studio-tools-for-unity"></a>Unity için Visual Studio araçlarına genel bakış
Bu bölümde, Unity sunar ve nasıl ile Unity daha üretken kullanabilmeniz için Visual Studio Araçları özellikler hakkında daha fazla bilgi edineceksiniz.  

 Unity için Visual Studio Araçları'yla (*VSTU*), oyun ve düzenleyici betikler C# ' ta oluşturma ve ardından güçlü, hata ayıklayıcı bulmak ve hataları düzeltmek için Visual Studio'yu kullanabilirsiniz. VSTU en son sürümünü sözdizimi Unity'nın ShaderLab gölgelendirici dil, daha iyi hata ayıklayıcı görselleştirmeler ve MonoBehavior Sihirbazı'nın geliştirilmiş kod oluşturma için renklendirme içerir. VSTU Unity proje dosyalarınıza, konsol iletileri ve daha az zaman için ve Unity Düzenleyicisi'nden kod yazarken geçiş harcayabilir şekilde oyununuzu Visual Studio'ya Başlat yeteneğini de getirir.  

 Bu özellikler hakkında daha fazla bilgi için okumaya devam edin.  

## <a name="integration-with-unity"></a>Unity ile tümleştirme  
 İleri ve geri her zaman Unity Düzenleyicisi ve Visual Studio arasında geçiş yapmak sahipse, Unity için visual Studio Araçları üretkenlik Geliştirici olmayacaktır. İşte bu nedenle Unity için Visual Studio Araçları çalışma Visual Studio ayrılmadan yapmaya devam yapmayı kolaylaştırır.  

-   **Unity Proje Gezgini** tüm Unity projenizi Unity Düzenleyicisi'nde görüntülenen aynı hiyerarşiye kullanarak Visual Studio içinde görüntüler.  

-   Unity Konsolu tümleştirmesi Visual Studio'nun hata penceresini sağ iç Unity konsol çıktısını görüntüler.  

-   Visual Studio'da - geri Unity için geçiş gerekli oyununuzu hata ayıklamayı Başlat yalnızca F5 tuşuna basın.  

## <a name="superior-debugging"></a>Üst hata ayıklama  
 C# komut dosyaları ve DLL'ler tek başına kullanılıp kullanılmadığını bağımsız olarak veya Unity Düzenleyicisi'nde hata ayıklamak için Unity oyununuzu Visual Studio'nun güçlü hata ayıklayıcı bağlayın. Visual Studio'dan beklediğiniz tüm hata ayıklama özelliklerini kullanabilirsiniz.  

-   Koşullu kesme noktaları da dahil olmak üzere kesme.  

-   Gözcü penceresi karmaşık ifadeler değerlendirin.  

-   İncelemek ve değişkenleri ve bağımsız değişken değerini değiştirin.  

-   Karmaşık nesne ve verileri yapılara detaya.  

 Ağınızdaki başka bir makine üzerinde çalışırken Unity oyununuzu bile ayıklayabilirsiniz.  

## <a name="productivity"></a>Üretkenliği  
 Yazma ve C# kod yeniden düzenleme için Visual Studio'nun kurulan üretkenlik yanı sıra, Unity için Visual Studio Araçları Unity geliştiriciler için fazladan verimlilik özellikleri sağlar.  

-   Unity'nın ShaderLab dil için renklendirme sözdizimi hataları haline gelmeden önce hataları, gölgelendiriciler nokta yardımcı olur. Yalnızca ShaderLab dosyalarınızı Visual Studio'da açın.  

-   MonoBehavior Sihirbazı'nı Unity davranışları listesini göz atmanızı sağlar ve aşina olmayabilir davranışları Demirbaş kod oluşturur. CTRL + SHIFT + M tuşuna basın.  

-   En çok kullandığınız Unity davranışlarla aşina olduğunuzda, hızlı MonoBehavior Sihirbazı bunları sağ parmaklarınızın ucunda koyar. CTRL + ALT + Q tuşlarına basın.  

-   Visual Studio'dan Unity belgelere erişebilir. Yalnızca hakkında bilgi edinin ve CTRL + ALT + M, CTRL + H basın istediğiniz API çağrısı vurgulayın.  

-   Bu özelliklerin tümü vb. klavye kısayollarıyla erişin.  

## <a name="visual-studio-tools-for-unity-api"></a>Unity API için Visual Studio Araçları  
 Özelleştirme ve sağlanan API'lerini kullanarak Unity için Visual Studio Araçları davranışını genişletebilirsiniz.  

-   Unity için visual Studio Araçları Visual Studio Unity konsola akışla aktarmak için bir günlük geri çağırma kaydeder. Bilgileri günlüğe Düzenleyicisi komut dosyalarınız varsa, Visual Studio, iletileri göndermek için aynı geri çağırma uygulamasına ekleyebilirsiniz. Daha fazla bilgi için günlüğü geri aramasını örneğe bakın.  

-   Unity için Visual Studio Araçları Unity stili geri çağırma ProjectFileGeneration kullanarak proje dosyalarını nasıl oluşturur değiştirebilirsiniz. Daha fazla bilgi için proje dosyası oluşturma örneğine bakın.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Unity giriş sayfası](http://unity3d.com)
