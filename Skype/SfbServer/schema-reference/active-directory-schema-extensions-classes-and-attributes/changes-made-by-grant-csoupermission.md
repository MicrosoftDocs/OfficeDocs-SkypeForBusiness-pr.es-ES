---
title: Cambios realizados por Grant CsOUPermission en Skype para Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Para delegar Skype para administración de Business Server, puede agregar permisos a especificado unidades organizativas (OU) para que los miembros de los grupos universales de RTC creados por la preparación del bosque pueden tener acceso a las unidades organizativas, sin ser miembros del grupo Administradores de dominio.
ms.openlocfilehash: 1313394248da2dcaeb9843bd689b2e2da3c51f96
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Cambios realizados por Grant CsOUPermission en Skype para Business Server
 
Para delegar Skype para administración de Business Server, puede agregar permisos a especificado unidades organizativas (OU) para que los miembros de los grupos universales de RTC creados por la preparación del bosque pueden tener acceso a las unidades organizativas, sin ser miembros del grupo Administradores de dominio. 
  
El cmdlet **Grant CsOuPermission** concede permisos a los objetos de la unidad organizativa especificada como se especifica en las tablas siguientes.
  
## <a name="granting-permission-for-user-objects"></a>Concesión de permisos de objetos de usuario

Al ejecutar el cmdlet **CsOuPermission de concesión** para objetos de usuario en una unidad organizativa, se otorgan a los grupos permisos tal como se muestra en la tabla siguiente.
  
**Permisos para objetos de usuario**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Este objeto sólo  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Mostrar el contenido  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Este objeto sólo  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Mostrar el contenido  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Este objeto sólo  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leer RTCUserSearchPropertySet  <br/> RTCUserProvisioningPropertySet de lectura  <br/> RTCPropertySet de lectura  <br/> Leer información pública  <br/> Leer información General  <br/> Leer restricciones de cuentas de usuario  <br/> |Objetos de usuario descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |Escribir RTCUserSearchPropertySet  <br/> Escriba msExchUCVoiceMailSettings  <br/> Escriba RTCUserProvisioningPropertySet  <br/> Escribir RTCPropertySet  <br/> Escriba proxyAddresses  <br/> |Objetos de usuario descendientes  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Concesión de permisos de objetos de equipo

Al ejecutar el cmdlet **CsOuPermission de concesión** para objetos de equipo en una unidad organizativa, se otorgan a los grupos permisos tal como se muestra en la tabla siguiente.
  
**Permisos para objetos de equipo**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Este objeto sólo  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Mostrar el contenido  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Este objeto sólo  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Mostrar el contenido  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Este objeto sólo  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leer información pública  <br/> Lectura validado---nombre de Host DNS  <br/> |Objetos descendientes de equipo  <br/> |
|RTCUniversalUserAdmins  <br/> |Leer información pública  <br/> Lectura validado---nombre de Host DNS  <br/> |Objetos descendientes de equipo  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concesión de permisos de los objetos AppContact o contacto

Al ejecutar el cmdlet **CsOuPermission de concesión** para objetos de contacto o AppContact en una unidad organizativa, los grupos se conceden permisos tal como se muestra en la tabla siguiente.
  
**Permisos concedidos para los objetos AppContact o contacto**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Este objeto sólo  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Mostrar el contenido  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Este objeto sólo  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Mostrar el contenido  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Este objeto sólo  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leer RTCUserSearchPropertySet  <br/> RTCUserProvisioningPropertySet de lectura  <br/> RTCPropertySet de lectura  <br/> Leer información pública  <br/> Leer información General  <br/> Leer la información de Personal  <br/> Leer restricciones de cuentas de usuario  <br/> |Objetos descendientes de contacto  <br/> |
|RTCUniversalUserAdmins  <br/> |Escribir RTCUserSearchPropertySet  <br/> Escriba otherIpPhone  <br/> Escribir displayName  <br/> Escribir descripción  <br/> Escriba el número de teléfono  <br/> Escriba msExchUCVoiceMailSettings  <br/> Escriba RTCUserProvisioningPropertySet  <br/> Escribir RTCPropertySet  <br/> Escriba proxyAddresses  <br/> |Objetos descendientes de contacto  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Concesión de permisos de objetos de dispositivo

Al ejecutar el cmdlet **CsOuPermission de concesión** para los objetos de dispositivo en una unidad organizativa, se otorgan a los grupos permisos tal como se muestra en la tabla siguiente.
  
**Permisos concedidos sobre objetos de dispositivo**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Este objeto sólo  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Mostrar el contenido  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Este objeto sólo  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Mostrar el contenido  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Este objeto sólo  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leer RTCUserSearchPropertySet  <br/> RTCUserProvisioningPropertySet de lectura  <br/> RTCPropertySet de lectura  <br/> Leer información pública  <br/> Leer la información de Personal  <br/> Leer información General  <br/> Leer restricciones de cuentas de usuario  <br/> |Objetos descendientes de contacto  <br/> |
|RTCUniversalUserAdmins  <br/> |Crear secundarios  <br/> Eliminar secundario  <br/> Eliminar árbol  <br/> |Contacto  <br/> |
|RTCUniversalUserAdmins  <br/> |Escribir displayName  <br/> Escribir descripción  <br/> Escriba el número de teléfono  <br/> |Objetos de usuario descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |Escribir RTCUserSearchPropertySet  <br/> Escriba otherIpPhone  <br/> Escribir displayName  <br/> Escribir descripción  <br/> Escriba el número de teléfono  <br/> Escriba msExchUCVoiceMailSettings  <br/> Escriba RTCUserProvisioningPropertySet  <br/> Escribir RTCPropertySet  <br/> Escriba proxyAddresses  <br/> |Objetos descendientes de contacto  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Concesión de permisos de objetos InetOrgPerson

Al ejecutar el cmdlet **CsOuPermission de concesión** de objetos InetOrgPerson en una unidad organizativa, se otorgan a los grupos permisos tal como se muestra en la tabla siguiente.
  
**Permisos concedidos sobre objetos InetOrgPerson**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar cambios de directorio  <br/> |Este objeto sólo  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Mostrar el contenido  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Este objeto sólo  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Mostrar el contenido  <br/> Leer todas las propiedades  <br/> Permisos de lectura  <br/> |Este objeto sólo  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leer RTCUserSearchPropertySet  <br/> RTCUserProvisioningPropertySet de lectura  <br/> RTCPropertySet de lectura  <br/> Leer la información de Personal  <br/> Leer información pública  <br/> Leer información General  <br/> Leer restricciones de cuentas de usuario  <br/> |Objetos inetOrgPerson descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |Escribir RTCUserSearchPropertySet  <br/> Escriba RTCUserProvisioningPropertySet  <br/> Escribir RTCPropertySet  <br/> Escriba proxyAddresses  <br/> |Objetos inetOrgPerson descendientes  <br/> |
   

