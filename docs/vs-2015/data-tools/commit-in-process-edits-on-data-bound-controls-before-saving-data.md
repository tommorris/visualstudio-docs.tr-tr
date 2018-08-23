---
title: Verileri kaydetmeden önce verilere bağlı denetimler üzerinde işlem içi düzenlemeler yürütme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- commiting edited records
- data-bound controls, in-process edits
- DataBinding class, commiting edited records
- hierarchical update, commiting edited records
- BindingSource class, commiting edited records
- EndEdit method
ms.assetid: 61af4798-eef7-468c-b229-5e1497febb2f
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bd56f9acfce7933d0bc89e7e86eb8083b9b1f867
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678911"
---
# <a name="commit-in-process-edits-on-data-bound-controls-before-saving-data"></a>Verileri kaydetmeden önce verilere bağlı denetimler üzerinde işlem içi düzenlemeler yürütme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [verileri kaydetmeden önce verilere bağlı denetimler üzerinde işlem içi düzenlemeler yürütme](https://docs.microsoft.com/visualstudio/data-tools/commit-in-process-edits-on-data-bound-controls-before-saving-data).  
  
  
Verilere bağlı denetimler değerleri düzenlerken, kullanıcılar güncelleştirilmiş değeri denetimin bağlı olduğu temel alınan veri kaynağına kaydetmek için geçerli kayıt devre dışı gitmeniz gerekir. Öğeleri sürüklediğinizde [veri kaynakları penceresi](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992) formunuza, koda bıraktığınız ilk öğeyi oluşturur **Kaydet** düğme tıklatma olayını, <xref:System.Windows.Forms.BindingNavigator>. Bu kod <xref:System.Windows.Forms.BindingSource.EndEdit%2A> yöntemi <xref:System.Windows.Forms.BindingSource>. Bu nedenle, çağrı <xref:System.Windows.Forms.BindingSource.EndEdit%2A> yöntemi yalnızca ilk oluşturulduğunda <xref:System.Windows.Forms.BindingSource> formuna eklenir.  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> Çağrı işleminde şu anda düzenlenmekte olan herhangi bir veriye bağlı denetim değişiklikleri kaydeder. Odak ve bu nedenle, bir veri bağlı denetim hala varsa tıklayın **Kaydet** denetim kaydedilir, gerçek kaydetme önce tüm bekleyen düzenlemeler düğmesine ( `TableAdapterManager.UpdateAll` yöntemi).  
  
 Bir kullanıcı kayıt işleminin bir parçası olarak değişikliklerin, taahhüt vermek zorunda kalmadan verileri kaydetmeyi denediğinde olsa bile, uygulamanızın otomatik olarak değişiklikleri yapılandırabilirsiniz işlem.  
  
> [!NOTE]
>  Tasarımcı ekler `BindingSource.EndEdit` kod yalnızca ilk öğe için bir forma bırakılan. Bu nedenle, bir çağırmak için kod satırı eklemeniz gerekir <xref:System.Windows.Forms.BindingSource.EndEdit%2A> yöntemi her <xref:System.Windows.Forms.BindingSource> form üzerinde. Bir satır kod çağırmak için el ile ekleyebilirsiniz <xref:System.Windows.Forms.BindingSource.EndEdit%2A> yöntemi her <xref:System.Windows.Forms.BindingSource>. Alternatif olarak, ekleme `EndEditOnAllBindingSources` forma yöntemi ve kaydetmeyi gerçekleştirmeden önce onu çağırabilir.  
  
 Aşağıdaki kod bir [LINQ (dil ile tümleşik sorgu)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) tüm yapılacağını sorgu <xref:System.Windows.Forms.BindingSource> bileşenleri ve çağrı <xref:System.Windows.Forms.BindingSource.EndEdit%2A> yöntemi her <xref:System.Windows.Forms.BindingSource> bir form üzerinde.  
  
## <a name="to-call-endedit-for-all-bindingsource-components-on-a-form"></a>Formdaki tüm BindingSource bileşenlerin EndEdit çağırmak için  
  
1.  İçeren formuna aşağıdaki kodu ekleyin <xref:System.Windows.Forms.BindingSource> bileşenleri.  
  
     [!code-csharp[VSProDataOrcasEndEditOnAll#1](../snippets/csharp/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/CS/Form1.cs#1)]
     [!code-vb[VSProDataOrcasEndEditOnAll#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/VB/Form1.vb#1)]  
  
2.  Kod form verilerini kaydetmek için tüm çağrıları hemen önce aşağıdaki satırı ekleyin ( `TableAdapterManager.UpdateAll()` yöntemi):  
  
     [!code-csharp[VSProDataOrcasEndEditOnAll#2](../snippets/csharp/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/CS/Form1.cs#2)]
     [!code-vb[VSProDataOrcasEndEditOnAll#2](../snippets/visualbasic/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da verilere Windows Forms denetimleri bağlama](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Hiyerarşik güncelleştirme](../data-tools/hierarchical-update.md)

