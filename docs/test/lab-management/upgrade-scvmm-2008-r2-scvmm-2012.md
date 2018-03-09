---
title: "SCVMM 2008 R2 SCVMM 2012'ye yükseltme | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Upgrade SCVMM 2008 R2 to SCVMM 2012, test lab
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 51d907dfe25d8f27065b2a4d8bbecaa3e98e42a1
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="upgrade-scvmm-2008-r2-to-scvmm-2012"></a>SCVMM 2008 R2 SCVMM 2012'ye yükseltme

SCVMM 2008 R2 ve SCVMM 2012 Team Foundation Server için Laboratuvar Yönetimini destekler. Team Foundation Server 2015 için Team Foundation Server 2013 yükseltiyorsanız ve SCVMM 2008 R2 SCVMM 2012'ye yükseltmeyi planlarsanız, Team Foundation Server 2015 yükseltmenizi tamamladıktan sonra SCVMM 2012'ye yükseltmenizi öneririz. Bu konu, Team Foundation Server 2015 tarihinde Laboratuvar Yönetimi kullanırken SCVMM 2008 R2 SCVMM 2012'ye yükseltme açıklar.
Laboratuvar Yönetimi **yok** SCVMM 2016 destekler. 

**Önemli:** SCVMM yükselttiğinizde, bazı adımlar, Team Foundation Server için bazı kesinti süresine neden olacak. Bu adımları bulabilirsiniz.

## <a name="upgrading-to-scvmm-2012"></a>SCVMM 2012'ye yükseltme

1. SCVMM 2012 yükleyici SCVMM 2012 Server SCVMM 2008 R2 sunucusunu yükseltmek için kullanın.

1. Konaklarınızdaki ve kitaplık paylaşımları SCVMM aracılarını yükseltin.

1. SCVMM bileşenlerinizi çalıştığından emin doğrulamak için SCVMM Yönetim konsolunu kullanın.

1. Team Foundation Server'ınızı uygulama katmanına tüm makinelerde SCVMM 2012 Yönetim Konsolu'nu yükleyin.

1. Kullanım **iisreset** Team Foundation Server web hizmeti yeniden başlatmak için komutu. Ardından Team Foundation Server iş aracıyı yeniden başlatın.

   **Dikkat:** bu adımı Team Foundation Server'ınızı hizmetlerde kesintiye neden.

1. Veri ve her proje koleksiyonu veritabanı şablonlarında SCVMM ile uyumlu olacak şekilde yükseltme 
   2012.

   Team Foundation Server'ınızı yükseltilmiş bir komut istemi açın ve aşağıdaki komutu girin:

   **C:\\Program Files\\Microsoft Team Foundation Server 14.0\\Araçları\> tfsconfig Laboratuvar /upgradeSCVMM /collectionName:\***

   Kullandığınızda **upgradeSCVMM** komutu, Team Foundation Server SCVMM sunucunuzda bu şablonu kullanan her takım projesi için yeni bir şablon nesnesi oluşturacak. Bu, şablonlarınızı herhangi bir veri kaybetmeden SCVMM 2012 ile uyumlu olacak şekilde yükseltilir sağlar. Ancak, yeni şablonlar oluşturduğunuzda, ekip projesi adını şablon adına eklenir.

   **Dikkat:**  
   Yeni şablon adı 64 karakterden büyükse, bu bir SCVMM hatasına neden olur. Bu hatayı gidermek için bu şablonları daha kısa bir ad vermeniz gerekir. Herhangi bir hata veya uyarı karşılaşırsanız, bu komutu çalıştırdığınızda bu hataları gidermek için sonraki bölüme bakın. Herhangi bir hata veya uyarı karşılaşmazsınız, yükseltme tamamlandıktan ve Laboratuvar Yönetimi ile SCVMM ortamları kullanmaya başlayabilirsiniz.

## <a name="resolving-errors-and-warnings-when-using-the-upgradescvmm-command"></a>UpgradeSCVMM komutunu kullanırken hataları ve Uyarıları gidermek

Kullandıktan sonra **upgradeSCVMM** komutu, herhangi bir hata veya uyarı alırsınız sonra Laboratuvar Yönetimini kullanmaya başlayabilmeniz için önce komutu yeniden çalıştırın çözümlemelidir. **UpgradeSCVMM** komut, hataları ve karşılaştığınız Uyarıları hakkında bilgi içeren bir günlük dosyası oluşturur. Günlük dosyasının konumunu çalıştırdığınızda görüntülenen **upgradeSCVMM** komutu.

**SCVMM hatası:** SCVMM hatası ile ilgili bir hata alırsanız, SCVMM iş geçmişi hatayla ilgili ek bilgi almak için kullanın. SCVMM hata çözdükten sonra yeniden **upgradeSCVMM** komutu.

## <a name="see-also"></a>Ayrıca bkz.

* [Var olan Laboratuvar Yönetim yapılandırmalarını değiştirme](https://msdn.microsoft.com/library/ee704508%28v=vs.140%29.aspx)
