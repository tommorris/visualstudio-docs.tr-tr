---
title: UML model öğe türleri | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UML API, types
ms.assetid: 25345a53-7246-4eb7-8ad9-0b695aa171a2
caps.latest.revision: 10
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: 5b8cb26c6e3d6cd51d087454d0b0c0700c1793db
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691317"
---
# <a name="uml-model-element-types"></a>UML model öğesi türleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [UML model öğe türleri](https://docs.microsoft.com/visualstudio/modeling/uml-model-element-types).  
  
Okuma ve bir programlama arabirimi aracılığıyla bir UML modeli ile düzenleme. Bu konuda hiyerarşisini öğe türleri özetlenmektedir. Hiyerarşi UML belirtiminde tanımlanmış aynıdır.  
  
 Her türün ayrıntıları sağlanan [UML modelleme genişletilebilirliği için API Başvurusu](../modeling/api-reference-for-uml-modeling-extensibility.md).  
  
## <a name="element-types"></a>Öğe türleri  
 Bu derlemede tanımlanan türlerin kümesidir `Microsoft.VisualStudio.Uml.Interfaces.dll`.  
  
 Her bir öğenin tam adı "`Microsoft.VisualStudio.Uml.`" ardından listelenen adı.  
  
 Kolaylık olması için bu listeyi Devralma Hiyerarşisi ayarlanır. Birden fazla üst bir türe sahip olduğunda, bir iki nokta (:) sonra ek türlerinden listelenir.  
  
```  
  
Classes.IElement  
|  Activities.IActivityGroup  
|  Classes.IComment  
|  Classes.IMultiplicityElement  
|  |  CompositeStructures.IConnectorEnd  
|  Classes.INamedElement  
|  |  Deployments.IDeployedArtifact  
|  |  Deployments.IDeploymentTarget  
|  |  |  Classes.IInstanceSpecification  
             : Deployments.IDeployedArtifact,  
               Deployments.IDeploymentTarget  
|  |  |  |  Classes.IEnumerationLiteral  
|  |  Interactions.IInteractionFragment  
|  |  |  Interactions.ICombinedFragment  
|  |  |  |  Interactions.IConsiderIgnoreFragment  
|  |  |  Interactions.IExecutionSpecification  
|  |  |  |  Interactions.IActionExecutionSpecification  
|  |  |  |  Interactions.IBehaviorExecutionSpecification  
|  |  |  Interactions.IInteraction  : CommonBehaviors.IBehavior  
|  |  |  Interactions.IInteractionOperand : Classes.INamespace  
|  |  |  Interactions.IInteractionUse  
|  |  |  Interactions.IOccurrenceSpecification  
|  |  |  |  Interactions.IExecutionOccurrenceSpecification  
|  |  |  |  Interactions.IMessageOccurrenceSpecification  
                   : Interactions.IMessageEnd  
|  |  |  |  |  Interactions.ILostFoundTarget  
|  |  |  |  Interactions.IOperandOccurrenceSpecification  
|  |  |  Interactions.IStateInvariant  
|  |  Interactions.ILifeline  
|  |  Interactions.IMessage  
|  |  Interactions.IMessageEnd  
|  |  Classes.INamespace  
|  |  |  Classes.IPackage  
             : Classes.IPackageableElement,  
              AuxiliaryConstructs.ITemplateableElement  
|  |  |  |  AuxiliaryConstructs.IModel  
|  |  |  Activities.IState  
|  |  Classes.IPackageableElement        
                   : AuxiliaryConstructs.IParameterableElement  
|  |  |  Classes.IConstraint  
|  |  |  |  Interactions.IInteractionConstraint  
|  |  |  CommonBehaviors.IEvent  
|  |  |  |  Interactions.IExecutionEvent  
|  |  |  |  CommonBehaviors.IMessageEvent  
|  |  |  |  |  CommonBehaviors.ICallEvent  
|  |  |  |  |  Interactions.IReceiveOperationEvent  
|  |  |  |  |  Interactions.IReceiveSignalEvent  
|  |  |  |  |  Interactions.ISendOperationEvent  
|  |  |  |  |  Interactions.ISendSignalEvent  
|  |  |  Classes.IType  
|  |  |  |  Classes.IClassifier : Classes.INamespace, Classes.IRedefinableElement, AuxiliaryConstructs.ITemplateableElement  
|  |  |  |  |  Deployments.IArtifact  
                   : Deployments.IDeployedArtifact  
|  |  |  |  |  |  Deployments.IDeploymentSpecification  
|  |  |  |  |  CommonBehaviors.IBehavioredClassifier  
|  |  |  |  |  |  UseCases.IActor  
|  |  |  |  |  |  Classes.IClass        
                         : CompositeStructures.IEncapsulatedClassifier  
|  |  |  |  |  |  |  CommonBehaviors.IBehavior  
|  |  |  |  |  |  |  |  Activities.IActivity  
|  |  |  |  |  |  |  Components.IComponent  
|  |  |  |  |  |  |  |  UseCases.ISubsystem  
|  |  |  |  |  |  |  Deployments.INode : IDeploymentTarget  
|  |  |  |  |  |  |  |  Deployments.IDevice  
|  |  |  |  |  |  |  |  Deployments.IExecutionEnvironment  
|  |  |  |  |  |  UseCases.IUseCase  
|  |  |  |  |  Classes.IDataType  
|  |  |  |  |  |  Classes.IEnumeration  
|  |  |  |  |  |  Classes.IPrimitiveType  
|  |  |  |  |  Classes.IInterface  
|  |  |  |  |  CompositeStructures.IStructuredClassifier  
|  |  |  |  |  |  CompositeStructures.IEncapsulatedClassifier  
|  |  |  Classes.IValueSpecification : Classes.ITypedElement  
|  |  |  |  Classes.IExpression  
|  |  |  |  Classes.IInstanceValue  
|  |  |  |  Classes.ILiteralSpecification  
|  |  |  |  |  Classes.ILiteralBoolean  
|  |  |  |  |  Classes.ILiteralInteger  
|  |  |  |  |  Classes.ILiteralNull  
|  |  |  |  |  Classes.ILiteralString  
|  |  |  |  |  Classes.ILiteralUnlimitedNatural  
|  |  |  |  Classes.IOpaqueExpression  
|  |  Classes.IRedefinableElement  
|  |  |  Activities.IActivityNode  
|  |  |  |  Activities.IControlNode  
|  |  |  |  |  Activities.IDecisionNode  
|  |  |  |  |  Activities.IFinalNode  
|  |  |  |  |  |  Activities.IActivityFinalNode  
|  |  |  |  |  Activities.IForkNode  
|  |  |  |  |  Activities.IInitialNode  
|  |  |  |  |  Activities.IJoinNode  
|  |  |  |  |  Activities.IMergeNode  
|  |  |  |  Activities.IExecutableNode  
|  |  |  |  |  Actions.IAction  
|  |  |  |  |  |  Actions.IAcceptEventAction  
|  |  |  |  |  |  Actions.ICreateObjectAction  
|  |  |  |  |  |  Actions.IInvocationAction  
|  |  |  |  |  |  |  Actions.ICallAction  
|  |  |  |  |  |  |  |  Actions.ICallBehaviorAction  
|  |  |  |  |  |  |  |  Actions.ICallOperationAction  
|  |  |  |  |  |  |  Actions.ISendSignalAction  
|  |  |  |  |  |  Actions.IOpaqueAction  
|  |  |  |  Activities.IObjectNode  : Classes.ITypedElement  
|  |  |  |  |  Activities.IActivityParameterNode  
|  |  |  |  |  Actions.IPin : Classes.IMultiplicityElement  
|  |  |  |  |  |  Actions.IInputPin  
|  |  |  |  |  |  Actions.IOutputPin  
|  |  |  UseCases.IExtensionPoint  
|  |  |  Classes.IFeature  
|  |  |  |  Classes.IBehavioralFeature  : Classes.INamespace  
|  |  |  |  |  Classes.IOperation  
                   : AuxiliaryConstructs.ITemplateableElement,  
                   AuxiliaryConstructs.IParameterableElement  
|  |  |  |  Classes.IStructuralFeature  
              : Classes.IMultiplicityElement,   
                Classes.ITypedElement  
|  |  |  |  |  Classes.IProperty  
                   : AuxiliaryConstructs.ITemplateableElement,   
                   CompositeStructures.IConnectableElement,   
                   Deployments.IDeploymentTarget  
|  |  |  |  |  |  CompositeStructures.IPort  
|  |  Classes.ITypedElement  
|  |  |  CompositeStructures.IConnectableElement  
             : AuxiliaryConstructs.IParameterableElement  
|  |  |  Classes.IParameter  : Classes.IMultiplicityElement, CompositeStructures.IConnectableElement  
|  AuxiliaryConstructs.IParameterableElement  
|  Classes.IProfileInstance  
  
|  Classes.IRelationship  
|  |  Activities.IActivityEdge : Classes.IRedefinableElement  
|  |  |  Activities.IControlFlow  
|  |  |  Activities.IObjectFlow  
|  |  Classes.IAssociation : IClassifier  
|  |  |  Deployments.ICommunicationPath  
|  |  CompositeStructures.IConnector  
|  |  Classes.IDirectedRelationship  
|  |  |  Classes.IDependency : Classes.IPackageableElement  
|  |  |  |  Classes.IAbstraction  
|  |  |  |  |  Deployments.IManifestation  
|  |  |  |  |  Classes.IRealization  
|  |  |  |  |  |  Classes.IInterfaceRealization  
|  |  |  |  Deployments.IDeployment  
|  |  |  |  Classes.IUsage  
|  |  |  UseCases.IExtend : Classes.INamedElement  
|  |  |  Classes.IGeneralization  
|  |  |  UseCases.IInclude : Classes.INamedElement  
|  |  |  Classes.IPackageImport  
|  |  |  AuxiliaryConstructs.ITemplateBinding  
|  Classes.IStereotypeInstance  
|  Classes.IStereotypePropertyInstance  
|  AuxiliaryConstructs.ITemplateableElement  
|  AuxiliaryConstructs.ITemplateParameter  
|  |  AuxiliaryConstructs.IClassifierTemplateParameter  
|  |  AuxiliaryConstructs.IOperationTemplateParameter  
|  AuxiliaryConstructs.ITemplateParameterSubstitution  
|  AuxiliaryConstructs.ITemplateSignature  
|  |  AuxiliaryConstructs.IRedefinableTemplateSignature   
             : Classes.IRedefinableElement  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [UML genişletmek için profil tanımlama](../modeling/define-a-profile-to-extend-uml.md)   
 [UML modelleri için doğrulama kısıtlamaları tanımlama](../modeling/define-validation-constraints-for-uml-models.md)   
 [UML Genişletilebilirlik Modellemesi için API Başvurusu](../modeling/api-reference-for-uml-modeling-extensibility.md)



