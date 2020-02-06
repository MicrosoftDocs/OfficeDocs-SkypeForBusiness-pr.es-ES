---
title: Cambios realizados por Grant-CsOUPermission en Skype empresarial Server
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
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Para delegar la administración de Skype empresarial Server, puede Agregar permisos a unidades organizativas (OU) especificadas de modo que los miembros de los grupos RTC universales creados por la preparación del bosque puedan tener acceso a las unidades organizativas sin ser miembros del grupo administradores de dominio.
ms.openlocfilehash: 8342d1801d2df91f940f02e8bfc05c3c5b91c4ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815528"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Cambios realizados por Grant-CsOUPermission en Skype empresarial Server
 
Para delegar la administración de Skype empresarial Server, puede Agregar permisos a unidades organizativas (OU) especificadas de modo que los miembros de los grupos RTC universales creados por la preparación del bosque puedan tener acceso a las unidades organizativas sin ser miembros del grupo administradores de dominio. 
  
El cmdlet **Grant-CsOuPermission** otorga permisos a objetos en la ou especificada, tal como se especifica en las tablas siguientes.
  
## <a name="granting-permission-for-user-objects"></a>Conceder permisos a los objetos de usuario

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de usuario en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.
  
**Permisos otorgados para objetos de usuario**

|**Mesa**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Solo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenido de la lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenido de la lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leer RTCUserSearchPropertySet  <br/> Leer RTCUserProvisioningPropertySet  <br/> Leer RTCPropertySet  <br/> Leer información pública  <br/> Leer información general  <br/> Leer las restricciones de la cuenta de usuario  <br/> |Objetos de usuario descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |Escribir RTCUserSearchPropertySet  <br/> Escribir msExchUCVoiceMailSettings  <br/> Escribir RTCUserProvisioningPropertySet  <br/> Escribir RTCPropertySet  <br/> Escribir proxyAddresses  <br/> |Objetos de usuario descendientes  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Concesión de permisos para objetos de equipo

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de equipo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.
  
**Permisos otorgados para objetos de equipo**

|**Mesa**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Solo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenido de la lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenido de la lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leer información pública  <br/> Lectura validada: nombre-DNS-host  <br/> |Objetos de equipo descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |Leer información pública  <br/> Lectura validada: nombre-DNS-host  <br/> |Objetos de equipo descendientes  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concesión de permisos para objetos de contacto o de AppContact

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de contacto o objetos de AppContact en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.
  
**Permisos concedidos para objetos de contacto o AppContact**

|**Mesa**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Solo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenido de la lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenido de la lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leer RTCUserSearchPropertySet  <br/> Leer RTCUserProvisioningPropertySet  <br/> Leer RTCPropertySet  <br/> Leer información pública  <br/> Leer información general  <br/> Leer información personal  <br/> Leer las restricciones de la cuenta de usuario  <br/> |Objetos de contacto descendiente  <br/> |
|RTCUniversalUserAdmins  <br/> |Escribir RTCUserSearchPropertySet  <br/> Escribir otherIpPhone  <br/> Escribir displayName  <br/> Escribir Descripción  <br/> Escribir telephoneNumber  <br/> Escribir msExchUCVoiceMailSettings  <br/> Escribir RTCUserProvisioningPropertySet  <br/> Escribir RTCPropertySet  <br/> Escribir proxyAddresses  <br/> |Objetos de contacto descendiente  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Conceder permisos a objetos de dispositivo

Al ejecutar el cmdlet **Grant-CsOuPermission** en una unidad organizativa, se conceden permisos a los grupos, como se muestra en la tabla siguiente.
  
**Permisos concedidos para objetos de dispositivo**

|**Mesa**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Solo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenido de la lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenido de la lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leer RTCUserSearchPropertySet  <br/> Leer RTCUserProvisioningPropertySet  <br/> Leer RTCPropertySet  <br/> Leer información pública  <br/> Leer información personal  <br/> Leer información general  <br/> Leer las restricciones de la cuenta de usuario  <br/> |Objetos de contacto descendiente  <br/> |
|RTCUniversalUserAdmins  <br/> |Crear elemento secundario  <br/> Eliminar hijo  <br/> Eliminar árbol  <br/> |Con  <br/> |
|RTCUniversalUserAdmins  <br/> |Escribir displayName  <br/> Escribir Descripción  <br/> Escribir telephoneNumber  <br/> |Objetos de usuario descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |Escribir RTCUserSearchPropertySet  <br/> Escribir otherIpPhone  <br/> Escribir displayName  <br/> Escribir Descripción  <br/> Escribir telephoneNumber  <br/> Escribir msExchUCVoiceMailSettings  <br/> Escribir RTCUserProvisioningPropertySet  <br/> Escribir RTCPropertySet  <br/> Escribir proxyAddresses  <br/> |Objetos de contacto descendiente  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Conceder permisos a objetos InetOrgPerson

Al ejecutar el cmdlet **Grant-CsOuPermission** para los objetos InetOrgPerson de una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.
  
**Permisos otorgados a los objetos InetOrgPerson**

|**Mesa**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Solo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenido de la lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenido de la lista  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leer RTCUserSearchPropertySet  <br/> Leer RTCUserProvisioningPropertySet  <br/> Leer RTCPropertySet  <br/> Leer información personal  <br/> Leer información pública  <br/> Leer información general  <br/> Leer las restricciones de la cuenta de usuario  <br/> |Objetos descendientes de inetOrgPerson  <br/> |
|RTCUniversalUserAdmins  <br/> |Escribir RTCUserSearchPropertySet  <br/> Escribir RTCUserProvisioningPropertySet  <br/> Escribir RTCPropertySet  <br/> Escribir proxyAddresses  <br/> |Objetos descendientes de inetOrgPerson  <br/> |
   

