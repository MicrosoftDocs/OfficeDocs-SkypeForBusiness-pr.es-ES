---
title: Cambios realizados por Grant-CsOUPermission en Skype Empresarial Server
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
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Para delegar Skype Empresarial Server administración, puede agregar permisos a unidades organizativas (UNIDADES organizativas) especificadas para que los miembros de los grupos universales RTC creados mediante la preparación del bosque puedan tener acceso a las unidades organizativas sin ser miembros del grupo Administradores de dominio.
ms.openlocfilehash: fc537ed927e5eb430b4c379218b4400b6ab12761a272f37bba68a281481c9531
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349722"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Cambios realizados por Grant-CsOUPermission en Skype Empresarial Server
 
Para delegar Skype Empresarial Server administración, puede agregar permisos a unidades organizativas (UNIDADES organizativas) especificadas para que los miembros de los grupos universales RTC creados mediante la preparación del bosque puedan tener acceso a las unidades organizativas sin ser miembros del grupo Administradores de dominio. 
  
El cmdlet **Grant-CsOuPermission** concede permisos a objetos en la unidad organizativa especificada como se indica en las tablas siguientes.
  
## <a name="granting-permission-for-user-objects"></a>Concesión de permisos para objetos de usuario

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de usuario en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.
  
**Permisos concedidos para objetos de usuario**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar los cambios de directorio  <br/> |Solo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenidos de la lista  <br/> Leer todas las propiedades  <br/> Leer permisos  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenidos de la lista  <br/> Leer todas las propiedades  <br/> Leer permisos  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet de lectura  <br/> RTCUserProvisioningPropertySet de lectura  <br/> RTCPropertySet de lectura  <br/> Public-Information de lectura  <br/> General-Information de lectura  <br/> User-Account-Restrictions de lectura  <br/> |Objetos de usuario descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet de escritura  <br/> msExchUCVoiceMailSettings de escritura  <br/> RTCUserProvisioningPropertySet de escritura  <br/> RTCPropertySet de escritura  <br/> proxyAddresses de escritura  <br/> |Objetos de usuario descendientes  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Concesión de permisos para objetos de equipo

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de equipo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente
  
**Permisos concedidos para objetos de equipo**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar los cambios de directorio  <br/> |Solo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenidos de la lista  <br/> Leer todas las propiedades  <br/> Leer permisos  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenidos de la lista  <br/> Leer todas las propiedades  <br/> Leer permisos  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Public-Information de lectura  <br/> Validated-DNS-Host-Name de lectura  <br/> |Objetos de equipo descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |Public-Information de lectura  <br/> Validated-DNS-Host-Name de lectura  <br/> |Objetos de equipo descendientes  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concesión de permisos para objetos Contact o AppContact

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos Contact u objetos AppContact en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.
  
**Permisos concedidos para objetos Contact o AppContact**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar los cambios de directorio  <br/> |Solo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenidos de la lista  <br/> Leer todas las propiedades  <br/> Leer permisos  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenidos de la lista  <br/> Leer todas las propiedades  <br/> Leer permisos  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet de lectura  <br/> RTCUserProvisioningPropertySet de lectura  <br/> RTCPropertySet de lectura  <br/> Public-Information de lectura  <br/> General-Information de lectura  <br/> Personal-Information de lectura  <br/> User-Account-Restrictions de lectura  <br/> |Objetos de contacto descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet de escritura  <br/> otherIpPhone de escritura  <br/> displayName de escritura  <br/> description de escritura  <br/> telephoneNumber de escritura  <br/> msExchUCVoiceMailSettings de escritura  <br/> RTCUserProvisioningPropertySet de escritura  <br/> RTCPropertySet de escritura  <br/> proxyAddresses de escritura  <br/> |Objetos de contacto descendientes  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Concesión de permisos para objetos de dispositivo

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos de dispositivo en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.
  
**Permisos concedidos para objetos de dispositivo**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar los cambios de directorio  <br/> |Solo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenidos de la lista  <br/> Leer todas las propiedades  <br/> Leer permisos  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenidos de la lista  <br/> Leer todas las propiedades  <br/> Leer permisos  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet de lectura  <br/> RTCUserProvisioningPropertySet de lectura  <br/> RTCPropertySet de lectura  <br/> Public-Information de lectura  <br/> Personal-Information de lectura  <br/> General-Information de lectura  <br/> User-Account-Restrictions de lectura  <br/> |Objetos de contacto descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |Crear secundario  <br/> Eliminar secundario  <br/> Eliminar árbol  <br/> |Contacto  <br/> |
|RTCUniversalUserAdmins  <br/> |displayName de escritura  <br/> description de escritura  <br/> telephoneNumber de escritura  <br/> |Objetos de usuario descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet de escritura  <br/> otherIpPhone de escritura  <br/> displayName de escritura  <br/> description de escritura  <br/> telephoneNumber de escritura  <br/> msExchUCVoiceMailSettings de escritura  <br/> RTCUserProvisioningPropertySet de escritura  <br/> RTCPropertySet de escritura  <br/> proxyAddresses de escritura  <br/> |Objetos de contacto descendientes  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Concesión de permisos para objetos InetOrgPerson

Al ejecutar el cmdlet **Grant-CsOuPermission** para objetos InetOrgPerson en una unidad organizativa, se conceden permisos a los grupos como se muestra en la tabla siguiente.
  
**Permisos concedidos para objetos InetOrgPerson**

|**Grupo**|**Permiso**|**Se aplica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replicar los cambios de directorio  <br/> |Solo este objeto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenidos de la lista  <br/> Leer todas las propiedades  <br/> Leer permisos  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenidos de la lista  <br/> Leer todas las propiedades  <br/> Leer permisos  <br/> |Solo este objeto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet de lectura  <br/> RTCUserProvisioningPropertySet de lectura  <br/> RTCPropertySet de lectura  <br/> Personal-Information de lectura  <br/> Public-Information de lectura  <br/> General-Information de lectura  <br/> User-Account-Restrictions de lectura  <br/> |Objetos inetOrgPerson descendientes  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet de escritura  <br/> RTCUserProvisioningPropertySet de escritura  <br/> RTCPropertySet de escritura  <br/> proxyAddresses de escritura  <br/> |Objetos inetOrgPerson descendientes  <br/> |
   

