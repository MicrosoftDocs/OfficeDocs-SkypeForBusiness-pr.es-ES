---
title: Cambios realizados por Grant-CsOUPermission en Skype para Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Para delegar Skype para administración de Business Server, puede agregar permisos a especificado unidades organizativas (OU) para que los miembros de los grupos universales de RTC creados por la preparación del bosque pueden tener acceso a las unidades organizativas sin ser miembros del grupo de administradores de dominio.
ms.openlocfilehash: 304f5d905f8839224013a2ce674b98405fd9ce8e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213707"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Cambios realizados por Grant-CsOUPermission en Skype para Business Server
 
Para delegar Skype para administración de Business Server, puede agregar permisos a especificado unidades organizativas (OU) para que los miembros de los grupos universales de RTC creados por la preparación del bosque pueden tener acceso a las unidades organizativas sin ser miembros del grupo de administradores de dominio. 
  
El cmdlet **Grant-CsOuPermission** concede permisos a objetos en la unidad organizativa especificada tal como se especifica en las tablas siguientes.
  
## <a name="granting-permission-for-user-objects"></a>Concesión de permisos para objetos de usuario

Cuando se ejecuta el cmdlet **Grant-CsOuPermission** para objetos de usuario en una unidad organizativa, los grupos se conceden permisos a tal como se muestra en la siguiente tabla.
  
**Permisos concedidos para objetos de usuario**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Sólo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenido de lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Sólo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenido de lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Sólo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet de lectura  <br/> RTCUserProvisioningPropertySet de lectura  <br/> RTCPropertySet de lectura  <br/> Public-Information de lectura  <br/> Leer información General  <br/> Lea las restricciones de cuenta de usuario  <br/> |Objetos de usuario descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet de escritura  <br/> MsExchUCVoiceMailSettings de escritura  <br/> RTCUserProvisioningPropertySet de escritura  <br/> RTCPropertySet de escritura  <br/> ProxyAddresses de escritura  <br/> |Objetos de usuario descendientes  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Concesión de permisos para objetos de equipo

Cuando se ejecuta el cmdlet **Grant-CsOuPermission** para objetos de equipo en una unidad organizativa, los grupos se conceden permisos a tal como se muestra en la siguiente tabla.
  
**Permisos concedidos para objetos de equipo**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Sólo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenido de lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Sólo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenido de lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Sólo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Public-Information de lectura  <br/> Lectura validan---nombre de Host DNS  <br/> |Objetos de equipo descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |Public-Information de lectura  <br/> Lectura validan---nombre de Host DNS  <br/> |Objetos de equipo descendientes  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concesión de permisos para objetos Contact o AppContact

Cuando se ejecuta el cmdlet **Grant-CsOuPermission** para objetos Contact u objetos AppContact en una unidad organizativa, se conceden a los grupos permisos tal como se muestra en la siguiente tabla.
  
**Permisos concedidos para objetos Contact o AppContact**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Sólo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenido de lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Sólo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenido de lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Sólo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet de lectura  <br/> RTCUserProvisioningPropertySet de lectura  <br/> RTCPropertySet de lectura  <br/> Public-Information de lectura  <br/> Leer información General  <br/> Personal-Information de lectura  <br/> Lea las restricciones de cuenta de usuario  <br/> |Objetos de contacto descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet de escritura  <br/> OtherIpPhone de escritura  <br/> Escribir displayName  <br/> Escribir descripción  <br/> TelephoneNumber de escritura  <br/> MsExchUCVoiceMailSettings de escritura  <br/> RTCUserProvisioningPropertySet de escritura  <br/> RTCPropertySet de escritura  <br/> ProxyAddresses de escritura  <br/> |Objetos de contacto descendientes  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Concesión de permisos para objetos de dispositivo

Cuando se ejecuta el cmdlet **Grant-CsOuPermission** para objetos de dispositivo en una unidad organizativa, los grupos se conceden permisos a tal como se muestra en la siguiente tabla.
  
**Permisos concedidos para objetos de dispositivo**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Sólo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenido de lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Sólo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenido de lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Sólo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet de lectura  <br/> RTCUserProvisioningPropertySet de lectura  <br/> RTCPropertySet de lectura  <br/> Public-Information de lectura  <br/> Personal-Information de lectura  <br/> Leer información General  <br/> Lea las restricciones de cuenta de usuario  <br/> |Objetos de contacto descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |Crear secundario  <br/> Eliminar secundario  <br/> Eliminar árbol  <br/> |Contacto  <br/> |
|RTCUniversalUserAdmins  <br/> |Escribir displayName  <br/> Escribir descripción  <br/> TelephoneNumber de escritura  <br/> |Objetos de usuario descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet de escritura  <br/> OtherIpPhone de escritura  <br/> Escribir displayName  <br/> Escribir descripción  <br/> TelephoneNumber de escritura  <br/> MsExchUCVoiceMailSettings de escritura  <br/> RTCUserProvisioningPropertySet de escritura  <br/> RTCPropertySet de escritura  <br/> ProxyAddresses de escritura  <br/> |Objetos de contacto descendientes  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Concesión de permisos para objetos InetOrgPerson

Cuando se ejecuta el cmdlet **Grant-CsOuPermission** para objetos InetOrgPerson en una unidad organizativa, los grupos se conceden permisos a tal como se muestra en la siguiente tabla.
  
**Permisos concedidos para objetos InetOrgPerson**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Sólo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenido de lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Sólo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenido de lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Sólo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet de lectura  <br/> RTCUserProvisioningPropertySet de lectura  <br/> RTCPropertySet de lectura  <br/> Personal-Information de lectura  <br/> Public-Information de lectura  <br/> Leer información General  <br/> Lea las restricciones de cuenta de usuario  <br/> |Objetos inetOrgPerson descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet de escritura  <br/> RTCUserProvisioningPropertySet de escritura  <br/> RTCPropertySet de escritura  <br/> ProxyAddresses de escritura  <br/> |Objetos inetOrgPerson descendientes  <br/> |
   

