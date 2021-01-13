---
title: Cambios de esquema en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Antes de implementar y operar Skype Empresarial Server, debe preparar los Servicios de dominio de Active Directory ampliando el esquema. Las extensiones de esquema agregan las clases y atributos necesarios para Skype Empresarial Server.
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813580"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Cambios de esquema en Skype Empresarial Server
 
Antes de implementar y operar Skype Empresarial Server, debe preparar los Servicios de dominio de Active Directory ampliando el esquema. Las extensiones de esquema agregan las clases y atributos necesarios para Skype Empresarial Server.

> [!NOTE]
> Si va a actualizar de Lync Server 2013 a Skype Empresarial Server 2015, no se realizan cambios de esquema y, por lo tanto, este artículo no es aplicable.
  
Skype Empresarial Server requiere varias clases y atributos nuevos y modifica algunas clases y atributos existentes. Además, mucha información de configuración para Skype Empresarial Server se almacena en el almacén de administración central en lugar de en AD DS como en versiones anteriores. La siguiente información se sigue almacenando en AD DS en Skype Empresarial Server:
  
- **Extensiones de esquema**:
    
  - Extensiones de objetos de usuario
    
  - Extensiones para las clases para mantener la compatibilidad con versiones anteriores compatibles con versiones anteriores de Lync Server.
    
- **Datos** (almacenados en el esquema extendido de Skype Empresarial Server y en clases de esquema existentes):
    
  - Identificador uniforme de recursos (URI) de SIP del usuario y otros parámetros de usuario
    
  - Objetos de contacto para aplicaciones como Grupo de respuesta y Operador de conferencia
    
  - Una referencia al almacén de administración central
    
  - Cuenta de autenticación Kerberos (un objeto de equipo opcional)
    
En este tema se describen los cambios de esquema de Active Directory requeridos por Skype Empresarial Server. No describe los cambios de esquema introducidos por versiones anteriores de Office Communications Server. Para obtener una lista de clases y sus descripciones, consulte Clases de esquema [y descripciones en Skype Empresarial Server.](schema-classes-and-descriptions.md) Para obtener una lista de atributos y sus descripciones, consulte Atributos de esquema [y descripciones en Skype Empresarial Server.](schema-attributes-and-descriptions.md) Para obtener una lista de clases con los atributos que pueden contener, consulte Atributos de [esquema por clase en Skype Empresarial Server.](schema-attributes-by-class.md)
  
El prefijo msRTCSIP identifica clases y atributos específicos de Skype Empresarial Server.
  
## <a name="new-active-directory-attributes"></a>Nuevos atributos de Active Directory

En la tabla siguiente se describen los atributos de Active Directory agregados por Skype Empresarial Server.
  
**Atributos agregados por Skype Empresarial Server**

|**Atributo**|**Descripción**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Este atributo de varios valores contiene los identificadores de las directivas de retención que se aplican al usuario. Las directivas de retención conservan los elementos del buzón del usuario durante toda la retención. Este atributo se comparte con Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Este es el identificador de grupo de enrutamiento SIP. Los usuarios del mismo grupo se registrarán en el mismo servidor front-end.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Este atributo se usa para almacenar el back-end de SQL Server reflejado usado por el grupo de servidores front-end.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Clases de Active Directory modificadas

En la tabla siguiente se describen las clases de Active Directory modificadas por Skype Empresarial Server.
  
**Clases modificadas por Skype Empresarial Server**

|**Clase**|**Cambio**|**Clase o atributo**|
|:-----|:-----|:-----|
|Usuario  <br/> |agregar: mayContain  <br/> agregar: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contacto  <br/> |agregar: mayContain  <br/> agregar: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |add: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |agregar: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

