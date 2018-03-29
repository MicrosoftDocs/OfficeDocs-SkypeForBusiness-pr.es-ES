---
title: Cambios de esquema en Skype para Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Antes de implementar y operar Skype para Business Server, debe preparar los servicios de dominio de Active Directory mediante la extensión del esquema. Las extensiones de esquema agregan las clases y atributos requeridos por Skype para Business Server.
ms.openlocfilehash: 42b4417311c557323535aa03053ccb03d95cc840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="schema-changes-in-skype-for-business-server"></a>Cambios de esquema en Skype para Business Server
 
Antes de implementar y operar Skype para Business Server, debe preparar los servicios de dominio de Active Directory mediante la extensión del esquema. Las extensiones de esquema agregan las clases y atributos requeridos por Skype para Business Server. 
  
Skype para Business Server requiere varias nuevas clases y atributos y modifica algunas clases existentes y los atributos. Además, mucha información de configuración de Skype para Business Server se almacena en el almacén de Administración Central, en lugar de en AD DS como en versiones anteriores. La información siguiente todavía se almacena en AD DS en Skype para Business Server:
  
- **Extensiones de esquema**:
    
  - Extensiones de objetos de usuario
    
  - Extensiones de clases para mantener la compatibilidad con versiones anteriores compatibles de Lync Server.
    
- **Datos** (almacenado en Skype para esquema extendido Business Server y en las clases de esquema existentes):
    
  - Usuario SIP Uniform Resource Identifier (URI) y otras configuraciones de usuario
    
  - Objetos Contact para aplicaciones como el grupo de respuesta y el operador de conferencia
    
  - Un puntero al almacén de Administración Central
    
  - Cuenta de autenticación de Kerberos (un objeto de equipo opcional)
    
Este tema describe los cambios de esquema de Active Directory requeridos por Skype para Business Server. Describe los cambios de esquema que se introdujeron en versiones anteriores de Office Communications Server. Para obtener una lista de las clases y sus descripciones, vea [clases de esquema y descripciones en Skype para Business Server](schema-classes-and-descriptions.md). Para obtener una lista de atributos y sus descripciones, consulte [descripciones de Skype para Business Server y atributos de esquema](schema-attributes-and-descriptions.md). Para obtener una lista de clases con los atributos pueden contener, vea [atributos de esquema por clase en Skype para Business Server](schema-attributes-by-class.md).
  
El prefijo msRTCSIP identifica las clases y atributos específicos de Skype para Business Server.
  
## <a name="new-active-directory-attributes"></a>Nuevos atributos de Active Directory

La tabla siguiente describe los atributos de Active Directory que se agregan por Skype para Business Server.
  
**Atributos agregados por Skype para Business Server**

|**Atributo**|**Descripción**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Este atributo multivalor contiene identificadores para contener las directivas que se aplican al usuario. Mantenga las políticas preservar elementos del buzón del usuario durante el tiempo que dure la suspensión. Este atributo se comparte con Exchange de 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Es el Id. de grupo de enrutamiento de SIP Los usuarios del mismo grupo se registran en el mismo servidor de Front-End.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Este atributo se utiliza para almacenar el servidor reflejado de SQL Server utilizado por el grupo de Front-End.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Clases de Active Directory modificado

La tabla siguiente describen las clases de Active Directory que se modifican por Skype para Business Server.
  
**Clases modificadas por Skype para Business Server**

|**Clase**|**Cambio**|**Clase o atributo**|
|:-----|:-----|:-----|
|Usuario  <br/> |agregar: mayContain  <br/> agregar: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contacto  <br/> |agregar: mayContain  <br/> agregar: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Destinatario de correo  <br/> |agregar: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |agregar: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

