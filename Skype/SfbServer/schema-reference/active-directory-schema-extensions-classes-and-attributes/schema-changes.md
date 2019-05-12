---
title: Cambios de esquema en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Antes de implementar y operar Skype para Business Server, debe preparar los servicios de dominio de Active Directory extendiendo el esquema. Las extensiones del esquema agregan las clases y atributos que se necesitan por Skype para Business Server.
ms.openlocfilehash: 5b6c3f036b1bc194331c721ea2d45564f0827d1c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924846"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Cambios de esquema en Skype para Business Server
 
Antes de implementar y operar Skype para Business Server, debe preparar los servicios de dominio de Active Directory extendiendo el esquema. Las extensiones del esquema agregan las clases y atributos que se necesitan por Skype para Business Server.

> [!NOTE]
> Si va a actualizar desde Lync Server 2013 a Skype para Business Server 2015, no se realizan cambios de esquema y, por tanto, en este artículo no se aplica.
  
Skype para Business Server requiere varias nuevas clases y atributos y modifica algunos atributos y clases existentes. Además, mucho información de configuración de Skype para Business Server se almacena en el almacén de Administración Central en lugar de hacerlo en AD DS como en versiones anteriores. La siguiente información aún se almacena en AD DS en Skype para Business Server:
  
- **Extensiones de esquema**:
    
  - Extensiones de objetos de usuario
    
  - Extensiones para las clases mantener la compatibilidad con versiones anteriores con versiones anteriores de Lync Server.
    
- **Datos** (almacenados en Skype para el esquema extendido de Business Server y en las clases de esquema existentes):
    
  - Usuario SIP Uniform Resource Identifier (URI) y otros parámetros de usuario
    
  - Objetos de contacto para aplicaciones como grupo de respuesta y operador de conferencia
    
  - Un puntero al almacén de Administración Central
    
  - Cuenta de autenticación de Kerberos (un objeto de equipo opcional)
    
En este tema se describe los cambios de esquema de Active Directory requeridos por Skype para Business Server. No se describen los cambios de esquema que se introdujeron en versiones anteriores de Office Communications Server. Para obtener una lista de las clases y sus descripciones, vea [las clases de esquema y descripciones de Skype para Business Server](schema-classes-and-descriptions.md). Para obtener una lista de atributos y sus descripciones, vea [atributos de esquema y descripciones de Skype para Business Server](schema-attributes-and-descriptions.md). Para obtener una lista de las clases con los atributos puede contener, vea [atributos de esquema por clase en Skype para Business Server](schema-attributes-by-class.md).
  
El prefijo msRTCSIP identifica clases y atributos que son específicos de Skype para Business Server.
  
## <a name="new-active-directory-attributes"></a>Nuevos atributos de Active Directory

En la siguiente tabla se describe los atributos de Active Directory que se agregan por Skype para Business Server.
  
**Atributos agregados por Skype para Business Server**

|**Atributo**|**Descripción**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Este atributo de varios valor contiene los identificadores para contener las directivas que se aplican al usuario. Mantenga las directivas de conservar los elementos del buzón para el usuario para la duración de la suspensión. Este atributo se comparte con Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Este es el SIP enrutamiento de identificador de grupo. Los usuarios en el mismo grupo registrará en el mismo servidor de Front-End.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Este atributo se usa para almacenar el reflejado SQL Server usado por el grupo de servidores Front-End.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Clases de Active Directory modificadas

En la siguiente tabla se describe las clases de Active Directory que se modifican por Skype para Business Server.
  
**Clases modificadas por Skype para Business Server**

|**Clase**|**Change**|**Clase o atributo**|
|:-----|:-----|:-----|
|Usuario  <br/> |agregar: mayContain  <br/> agregar: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contacto  <br/> |agregar: mayContain  <br/> agregar: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Destinatario de correo  <br/> |agregar: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |agregar: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

