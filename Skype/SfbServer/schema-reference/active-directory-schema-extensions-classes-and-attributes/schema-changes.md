---
title: Cambios de esquema en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Antes de implementar y trabajar con Skype empresarial Server, debe preparar los servicios de dominio de Active Directory extendiendo el esquema. Las extensiones de esquema agregan las clases y los atributos que necesita Skype empresarial Server.
ms.openlocfilehash: 0c3765fe36b252cc03218a3fa4365c5cc36c7f48
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815488"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Cambios de esquema en Skype empresarial Server
 
Antes de implementar y trabajar con Skype empresarial Server, debe preparar los servicios de dominio de Active Directory extendiendo el esquema. Las extensiones de esquema agregan las clases y los atributos que necesita Skype empresarial Server.

> [!NOTE]
> Si está actualizando desde Lync Server 2013 a Skype empresarial Server 2015, no se realizarán cambios de esquema y, por lo tanto, no se aplicará este artículo.
  
Skype empresarial Server requiere varias clases y atributos nuevos y modifica algunas clases y atributos existentes. Además, la información de configuración de Skype empresarial Server se almacena en el almacén de administración central, en lugar de en AD DS, como en versiones anteriores. La siguiente información se almacena aún en AD DS en Skype empresarial Server:
  
- **Extensiones de esquema**:
    
  - Extensiones de objetos de usuario
    
  - Extensiones para las clases para mantener la compatibilidad con versiones anteriores compatibles de Lync Server.
    
- **Datos** (almacenados en el esquema extendido de Skype empresarial Server y en las clases de esquema existentes):
    
  - Identificador uniforme de recursos (URI) SIP de usuario y otra configuración de usuario
    
  - Objetos de contacto para aplicaciones como el operador de conferencia y el grupo de respuesta
    
  - Puntero al almacén de administración central
    
  - Cuenta de autenticación Kerberos (un objeto de equipo opcional)
    
En este tema se describen los cambios de esquema de Active Directory que necesita Skype empresarial Server. No se describen los cambios de esquema introducidos por versiones anteriores de Office Communications Server. Para obtener una lista de las clases y sus descripciones, vea [clases de esquema y descripciones de Skype empresarial Server](schema-classes-and-descriptions.md). Para obtener una lista de atributos y sus descripciones, consulte [atributos y descripciones del esquema en Skype empresarial Server](schema-attributes-and-descriptions.md). Para obtener una lista de las clases con los atributos que pueden contener, consulte [atributos de esquema por clase en Skype empresarial Server](schema-attributes-by-class.md).
  
El prefijo msRTCSIP identifica clases y atributos específicos de Skype empresarial Server.
  
## <a name="new-active-directory-attributes"></a>Nuevos atributos de Active Directory

En la siguiente tabla se describen los atributos de Active Directory que agrega Skype empresarial Server.
  
**Atributos agregados por Skype empresarial Server**

|**Atributo**|**Descripción**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Este atributo de valor múltiple contiene los identificadores para las directivas de retención que se aplican al usuario. Las directivas de retención mantienen los elementos del buzón de correo para el usuario durante el período de espera. Este atributo se comparte con Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Este es el identificador de grupo de enrutamiento SIP. Los usuarios del mismo grupo se registrarán en el mismo servidor front-end.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Este atributo se usa para almacenar el back-end de SQL Server reflejado usado por el grupo de servidores front-end.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Clases de Active Directory modificadas

En la siguiente tabla se describen las clases de Active Directory que modifica Skype empresarial Server.
  
**Clases modificadas por Skype empresarial Server**

|**Las**|**Cambio**|**Clase o atributo**|
|:-----|:-----|:-----|
|Usuario  <br/> |Agregar: mayContain  <br/> Agregar: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Con  <br/> |Agregar: mayContain  <br/> Agregar: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Destinatario de correo  <br/> |Agregar: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Agregar: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

