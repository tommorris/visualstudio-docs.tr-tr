---
title: Python için Azure SDK
description: Python için Azure SDK'sı, Microsoft Azure hizmetlerinden herhangi bir platformda çalışan Python uygulamaları kullanmasını kolaylaştırır.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: 4dd7e5841db4c05de5607f9aefe7b9a3a36fee19
ms.sourcegitcommit: 4f82c178b1ac585dcf13b515cc2a9cb547d5f949
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39341244"
---
# <a name="azure-sdk-for-python"></a>Python için Azure SDK

Python için Azure SDK'sını kullanma ve Windows, Mac OSX ve Linux'ta çalışan uygulamalar Microsoft Azure hizmetlerini yönetmenize daha kolay hale getirir.

## <a name="installation"></a>Yükleme

Azure SDK'ın yüklendiği [Python paket dizinini](https://pypi.python.org/pypi/azure).

Yükleme **en son kararlı sürüm** (Python 2.7 ve 3.x gibi destekler):

```command
pip install azure
```

De izleyebilirsiniz [yüklemeniz Python ve SDK'sı](https://docs.microsoft.com/azure/python-how-to-install/) Azure belgeleri.

## <a name="documentation"></a>Belgeler

Belgeler bulunabilir [python.readthedocs.org için azure SDK'sı](https://docs.microsoft.com/en-us/python/azure/?view=azure-python).

[Python Geliştirici Merkezi için Azure SDK'sı](http://azure.microsoft.com/develop/python/) de faydalı kaynaklara, birçok öğretici dahil olmak üzere birçok vardır:

- Web apps ile oluşturma [Django](/azure/app-service-web/web-sites-python-create-deploy-django-app), [Flask](/azure/app-service-web/web-sites-python-create-deploy-flask-app), ve [Bottle](/azure/app-service-web/web-sites-python-create-deploy-bottle-app).
- [BLOB Depolama](/azure/storage/storage-python-how-to-use-blob-storage)
- [Tablo depolama](/azure/storage/storage-python-how-to-use-table-storage)
- [Kuyruk depolama](/azure/storage/storage-python-how-to-use-queue-storage)
- [Azure Cosmos DB](/azure/cosmos-db/sql-api-python-application)
- [Service Bus kuyrukları](/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
- [Hizmet veri yolu konuları/abonelikleri](/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
- [Hizmet Yönetimi](/azure/cloud-services/cloud-services-python-how-to-use-service-management)

Belgeler olmadan ortak API'ler için birim testleri içindeki [SDK'sı GitHub deposu](https://github.com/Azure/azure-sdk-for-python) iyi bir bilgi kaynağı olan:

- [Birim testleri](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [Service Bus birim testleri](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [Hizmet Yönetimi birim testleri](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)

## <a name="support"></a>Destek

Git deposu için SDK'sı şu konumdadır [ https://github.com/Azure/azure-sdk-for-python ](https://github.com/Azure/azure-sdk-for-python).

[Deponun sorunlar dosya](https://github.com/Azure/azure-sdk-for-python/issues) problemleri bulun ya da SDK'sının kullanım ile ilgili sorularınız varsa.
