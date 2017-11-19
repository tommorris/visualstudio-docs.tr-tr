---
title: '&#39; teki Visual Studio 2017 SDK''deki yenilikler | Microsoft Docs'
ms.custom: 
ms.date: 10/31/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9efcf0a3-dbde-4cab-8ed3-425826a48b2e
caps.latest.revision: "1"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0be477d54ffeab52c415890c7d95447fa3f55ffc
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="what39s-new-in-the-visual-studio-2017-sdk"></a>&#39; teki Visual Studio 2017 SDK'deki yenilikler

Visual Studio SDK'sı için Visual Studio 2017 aşağıdaki yeni ve güncelleştirilmiş özelliklere sahiptir.

## <a name="vsix-v3-format"></a>VSIX v3 biçimi

Visual Studio 2017 yeni hafif yüklemesini desteklemek için VSIX uzantı bildirim biçimi sürüm 3 (VSIX v3) güncelleştirildi.

Yeni biçim desteği vardır:

* Açıkça algılanabilir ve tarafından VSIXInstaller yüklü için Önkoşullar bildirme.
* Genişletme yüklemesinin derlemelerini Ngen'ing.
* Her zamanki uzantısı kök dışında varlıklar yükleniyor.

Bu değişiklikler hakkında bilgi edinmek için aşağıdaki konulara bakın:

* [Genişletilebilirlik 2017 için yapılan değişiklikler](breaking-changes-2017.md)
* [VSIX v3 Ngen desteği](ngen-support.md)
* [Uzantıları klasörünün dışında yükleme](set-install-root.md)
* [Sık sorulan sorular için Visual Studio 2017 genişletilebilirliği](faq-2017.md)

## <a name="migrating-extensibility-project-to-visual-studio-2017"></a>Visual Studio 2017 için geçirme genişletilebilirlik projesi

Genişletilebilirlik projelerinizi ve bunların VSIX bildirimleri için Visual Studio 2017 güncelleştirme konusunda bilgi edinmek için [nasıl yapılır: Visual Studio 2017 genişletilebilirlik projelerine geçirmek](how-to-migrate-extensibility-projects-to-visual-studio-2017.md).

## <a name="custom-project-and-item-templates"></a>Özel proje ve öğe şablonları

Visual Studio 2017 içinde başlayarak, özel Proje ve öğe şablonları için tarama artık gerçekleştirilir. Bunun yerine, uzantı bu şablonları yükleme konumunu tanımlayan şablon bildirim dosyası sağlamanız gerekir. Visual Studio 2017 VSIX uzantılarınızın güncelleştirmek için kullanabilirsiniz. Uzantınızı bir MSI kullanarak dağıtırsanız, şablon bildirim dosyalarını el ile oluşturmanız gerekir. Daha fazla bilgi için bkz: [yükseltme özel Proje ve öğe şablonları için Visual Studio 2017](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-2017.md). Şablon bildirim şeması belgelenen [Visual Studio şablon bildirim şema başvurusu](../extensibility/visual-studio-template-manifest-schema-reference.md).

## <a name="updated-extension-performance-guidelines"></a>Güncelleştirilmiş uzantısı performans kuralları

Yeni bir [nasıl yapılır: uzantı performans tanılamak](how-to-diagnose-extension-performance.md) konu altında [yönetme VSPackages](managing-vspackages.md) algılamak ve Visual Studio uzantısı etkisini çözümlemek nasıl göstermek için başlangıç ve çözüm kez yükler.
