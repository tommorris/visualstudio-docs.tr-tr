---
title: Belgelere güven verme | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- security [Office development in Visual Studio], trust
- inclusion lists [Office development in Visual Studio], about inclusion lists
- trust [Office development in Visual Studio], 2007 Office system
- granting trust [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e8556f77b74ee1dab6a257f5ed3634da4bf798cd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="granting-trust-to-documents"></a>Belgelere Güven Verme
  Belge düzeyi projesi uygulama düzeyi projelere aynı güvenlik gereksinimlerine sahiptir: bir sertifika ile bildirimleri imzalama veya güven istemi tıklatarak. Ayrıca, belge veya çalışma kitabı güvenilir bir konum olarak belirlenmiş bir dizinde yer almalıdır.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="trusted-locations"></a>Güvenilir konumlar  
 Uygulamalarda [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] ve Office 2010 güven nerede kullanıcılar yapılandırabilir güvenilir konumlar gibi güvenlik ve gizlilik ayarları merkezleri. Office çözümleri için yerel bilgisayar güvenilen bir konum olarak kabul edilir. Ancak, daha yüksek risk nedeniyle geçici bir klasör sistem, her kullanıcı ve Internet Explorer gibi güvenilir olamaz belirli dizinleri vardır.  
  
 Güven Merkezi hakkında daha fazla bilgi için bkz: [güvenlik ve ilkeleri ve Office 2010 ayarlarında](http://go.microsoft.com/fwlink/?LinkId=89202). Oluşturma, yönetme, kaldırmak ve güvenilir klasörlerini yapılandırma hakkında daha fazla bilgi için bkz: [güvenilir konumlar ve güvenilen yayımcılar ayarlarını 2007 Office sistemi yapılandırmak](http://go.microsoft.com/fwlink/?LinkId=89203) ve [oluşturma, kaldırma veya değiştirme bir güvenilir, dosyaları için konum](https://support.office.com/en-au/article/Create-remove-or-change-a-trusted-location-for-your-files-f5151879-25ea-4998-80a5-4208b3540a62).  
  
## <a name="security-considerations-for-office-solutions"></a>Office çözümleri için güvenlik konuları  
 Güvenilir konumlara eklemek için hangi klasörlerin göz önüne aldığınızda birkaç güvenlik sorunları vardır:  
  
-   Yerel klasör daha güvenli ve örtük olarak güvenilir olarak kabul edilir. Dosya paylaşımları gibi uzak konumlar güvenilir konumlar olarak işaretlenmesi gerekir.  
  
-   Bir dizin güvenilir konumlara eklediğinizde, bu eylem yalnızca Office çözümleri için aynı zamanda VBA ve ActiveX kod için tam güven verir. Bu nedenle, güvenilen kök dizini ve klasörleri olarak atanmamalıdır Belgelerim.  
  
-   Belge güvenilen konumları kullanarak güvenilen rağmen özelleştirme güvenmeyi ek izinler gerekir. Bir sertifika ile bildirimleri imzalama, güven istemi tıklatarak veya Program dosyaları dizinine Office çözümü yükleme kullanarak özelleştirme tam güven verebilirsiniz.  
  
-   Belge ya da bir belge düzeyi çözümü çalışma kitabını derlemeyle aynı dizinde veya farklı bir dizinde depolayabilirsiniz. Örneğin, belgeyi bir SharePoint sunucusu üzerine bulunamıyor ve bir ağ dosya paylaşımında derleme bulunamıyor. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint sunucusu kullanarak ClickOnce tarafından için belge düzeyi Office çözümü yayımlama](http://msdn.microsoft.com/en-us/2408e809-fb78-42a1-9152-00afa1522e58).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerine güven verme](../vsto/granting-trust-to-office-solutions.md)   
 [Office çözüm güvenliğinde sorunu giderme](../vsto/troubleshooting-office-solution-security.md)   
 [Office Çözümleri Güvenliğini Sağlama](../vsto/securing-office-solutions.md)  
  
  