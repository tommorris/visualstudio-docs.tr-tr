---
title: 'Nasıl yapılır: belgelere yönetilen kod uzantıları ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- managed code extensions [Office development in Visual Studio], attaching
- documents [Office development in Visual Studio], managed code extensions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: fe415cfb0635f133baf191f027ca7ae0111989a9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-attach-managed-code-extensions-to-documents"></a>Nasıl Yapılır: Belgelere Yönetilen Kod Uzantıları Ekleme
  Varolan Microsoft Office Word belgesine veya Microsoft Office Excel çalışma kitabı için özelleştirme derlemesi ekleyebilirsiniz. Belge veya çalışma kitabı Microsoft Office projeleri ve Visual Studio geliştirme araçları tarafından desteklenen herhangi bir dosya biçiminde olabilir. Daha fazla bilgi için bkz: [belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Bir Word veya Excel belgesi özelleştirme iliştirmek için kullanmak <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> yöntemi <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> sınıfı. Çünkü <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> sınıfı, Microsoft Office yüklü olmayan bir bilgisayarda çalışacak şekilde tasarlanmıştır, doğrudan Microsoft Office geliştirme (örneğin, bir konsolu veya Windows Forms uygulaması) ilişkili çözümlerinde bu yöntemi kullanabilirsiniz.  
  
> [!NOTE]  
>  Özelleştirme kodunu belirtilen belge yok denetimleri görüyorsa yüklenmesi başarısız olur.  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [yapmak I: ekleme veya ayırma bir Word belgesi VSTO derlemesinden?](http://go.microsoft.com/fwlink/?LinkId=136782).  
  
### <a name="to-attach-managed-code-extensions-to-a-document"></a>Yönetilen kod uzantıları belgeye eklemek için  
  
1.  Microsoft Office gibi bir konsol uygulaması gerektirmez proje veya Windows Forms projesi Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll ve Microsoft.VisualStudio.Tools.Applications.Runtime.dll bir başvuru ekleyin derlemeler.  
  
2.  Aşağıdakileri ekleyin **içeri aktarmalar** veya **kullanarak** kod dosyanın en üstüne deyimleri.  
  
     [!code-csharp[Trin_VstcoreDeployment#4](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#4)]
     [!code-vb[Trin_VstcoreDeployment#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#4)]  
  
3.  Statik çağrı <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> yöntemi.  
  
     Aşağıdaki kod örneğinde <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> aşırı yükleme. Bu aşırı belgenin tam yolunu alır ve bir <xref:System.Uri> belgeye iliştirmek istediğiniz özelleştirme için dağıtım bildiriminin konumunu belirtir. Bu örnek bir Word belgesi adlı varsayar **WordDocument1.docx** masaüstünde olduğu ve dağıtım bildirimi adlı bir klasörde bulunan **Yayımla** olan Ayrıca masaüstünde.  
  
     [!code-csharp[Trin_VstcoreDeployment#3](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#3)]
     [!code-vb[Trin_VstcoreDeployment#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#3)]  
  
4.  Projeyi oluşturun ve uygulamayı özelleştirme iliştirmek istediğiniz bilgisayarda çalıştırın. Bilgisayar Office yüklü çalışma zamanı için Visual Studio 2010 Araçları olması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ServerDocument sınıfını kullanarak bir sunucu üzerinde belgeleri yönetme](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)   
 [Nasıl yapılır: belgelerden yönetilen kod uzantılarını kaldırma](../vsto/how-to-remove-managed-code-extensions-from-documents.md)   
 [Office Çözümlerinde Uygulama ve Dağıtım Bildirimleri](../vsto/application-and-deployment-manifests-in-office-solutions.md)  
  