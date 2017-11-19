---
title: "Office çözümünü dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ClickOnce deployment [Office development in Visual Studio], event viewer
- deploying applications [Office development in Visual Studio], event viewer
- Office applications [Office development in Visual Studio], deploying Office solutions
- Office development in Visual Studio, deploying Office solutions
- ClickOnce deployment [Office development in Visual Studio], troubleshooting
- deploying applications [Office development in Visual Studio], Office solutions (2007 system)
- Office development in Visual Studio, troubleshooting
- Office development in Visual Studio, event viewer
- ClickOnce deployment [Office development in Visual Studio], about ClickOnce solution deployments
- Office solutions [Office development in Visual Studio], deploying
- deploying applications [Office development in Visual Studio], troubleshooting
- solutions [Office development in Visual Studio], deploying Office solutions (2007 system)
ms.assetid: 4cdf4bc6-72c5-4166-8019-d5fd61281079
caps.latest.revision: "78"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5e9511e8fca3e1a6b02b764f21acf71c6535fc05
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="deploying-an-office-solution"></a>Office Çözümünü Dağıtma
  Office çözümlerini ClickOnce veya Windows Installer kullanarak dağıtabilirsiniz. ClickOnce kullandığınızda, çözümünüzü dağıtmak ve güncelleştirmek için gerekli adımların sayısını azaltmış olursunuz. Windows Installer kullanırsanız, çözümün nasıl yükleneceği ve kullanıcı çözümünüzü yüklediğinde kurulum programının hangi sayfaları görüntüleyeceği üzerinde denetim sahibi olursunuz.  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
## <a name="deploying-a-solution-by-using-clickonce"></a>Çözümü ClickOnce Kullanarak Dağıtma  
 Bir çözümü ClickOnce kullanarak dağıtırken, kullanıcıların yükleyip çalıştırabileceği merkezi bir konumda çözümü yayınlarsınız. Kullanıcılara yeni bir kurulum programı dağıtmaya gerek kalmadan çözümü güncelleştirebilirsiniz.  Bu dağıtım seçeneği daha basittir, ancak özel kurulum sayfalarını kullanıcılara gösteremezsiniz. Ayrıca çözümlerin, birden fazla kullanıcısı olan bilgisayarlara birden fazla kez yüklenmesi gerekir. Bkz: [ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
## <a name="deploying-a-solution-by-using-windows-installer"></a>Çözümü Windows Installer Kullanarak Dağıtma  
 Çözümü Windows Installer kullanarak dağıtırken, kullanıcılara bir kurulum programı dağıtırsınız ve kullanıcılar da bu programı kullanarak çözümü yükler. Kurulum programı, çözümü yalnızca geçerli kullanıcı için yüklemek yerine, bir bilgisayarın tüm kullanıcıları için aynı anda yükleyebilir. Çözümünüzü bilgisayarlarına yüklediklerinde kullanıcıların göreceği seçenekler üzerinde biraz daha fazla denetim sahibi olursunuz. Örneğin, bir lisans sözleşmesi gösterebilir veya kullanıcıların çözüme ait belirli bileşenleri yüklemelerine olanak sağlayabilirsiniz. Ancak, çözümü güncelleştirecek olursanız yeni bir kurulum programı dağıtmanız gerekir. Bkz: [Windows Installer kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-windows-installer.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md)   
 [ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Windows Installer kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-windows-installer.md)   
 [Office çözümü dağıtımında sorunu giderme](../vsto/troubleshooting-office-solution-deployment.md)  
  
  