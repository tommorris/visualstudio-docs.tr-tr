---
title: "Bağımlılık diyagramlarını genişletme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency diagrams, creating extensions
- layer models
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 076964379f0903945767110a3c19edb87d3c7092
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="extend-dependency-diagrams"></a>Bağımlılık diyagramlarını genişletme
Kod oluşturma ve bağımlılık diyagramları güncelleştirir ve Visual Studio'da bağımlılık diyagramları karşı program kodunuzu yapısını doğrulamak için yazabilirsiniz. Diyagramları (içerik) kısayol menüsünde görüntülenen, sürükle ve bırak hareketleri özelleştirmek ve katman modeli metin şablonlardan erişim komutları ekleyebilirsiniz. Bu uzantılar bir Visual Studio Tümleştirme Uzantısı (VSIX) paketini ve diğer Visual Studio kullanıcılara dağıtın.  
  
 Bağımlılık diyagramları hakkında daha fazla bilgi için bkz:  
  
-   [Bağımlılık Diyagramları: Başvuru](../modeling/layer-diagrams-reference.md)  
  
-   [Bağımlılık Diyagramları: Yönergeler](../modeling/layer-diagrams-guidelines.md)  
  
-   [Kodunuz aracılığıyla bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)  
  
-   [Bağımlılık diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md)  
  
##  <a name="prereqs"></a>Gereksinimleri  
 Aşağıdaki katman uzantılar geliştirmek üzere istediğiniz bilgisayarda yüklü olması gerekir:  
  
-   Visual Studio  
  
-   [Visual Studio SDK](../extensibility/visual-studio-sdk.md)  
  
-   Visual Studio SDK Modelleme  


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

  
 Visual Studio'nun katman uzantılarınızın çalıştırmak istediğiniz bilgisayarda yüklü olan uygun bir sürümünün bulunması gerekir. Daha fazla bilgi için bkz: [katman modeli uzantısı dağıtma](../modeling/deploy-a-layer-model-extension.md).  
  
 Visual Studio hangi sürümlerinin bağımlılık diyagramları desteklediğini görmek için bkz: [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Bağımlılık diyagramlarına komut ve hareket ekleme](../modeling/add-commands-and-gestures-to-layer-diagrams.md)  
  
 [Bağımlılık diyagramlarına özel mimari doğrulaması ekleme](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)  
  
 [Bağımlılık diyagramlarına özel özellikler ekleme](../modeling/add-custom-properties-to-layer-diagrams.md)  
  
 [Program kodunda katman modellerini gezinme ve güncelleştirme](../modeling/navigate-and-update-layer-models-in-program-code.md)  
  
 [Katman modeli uzantısı dağıtma](../modeling/deploy-a-layer-model-extension.md)  
  
 [Bağımlılık diyagramları için uzantı sorunlarını giderme](../modeling/troubleshoot-extensions-for-layer-diagrams.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımlılık diyagramları: başvuru](../modeling/layer-diagrams-reference.md)   
 [Bağımlılık diyagramları: yönergeler](../modeling/layer-diagrams-guidelines.md)   
 [Kodunuz aracılığıyla bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)   
 [Bağımlılık diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md)   
