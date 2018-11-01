---
title: "Lync Server 2013: Agregar dominios de usuarios y grupos usuarios a categoría de salón"
TOCTitle: Agregar dominios de usuarios y grupos de usuarios a la categoría de salón
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ215884(v=OCS.15)
ms:contentKeyID: 48277104
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Agregar dominios de usuarios y grupos de usuarios a la categoría de salón en Lync Server 2013

 

_**Última modificación del tema:** 2014-02-07_

Para agregar grupos más grandes de usuarios a un salón de chat, consulte [Configurar categorías en Lync Server 2013](lync-server-2013-configure-categories.md) y [Administrar categorías](manage-categories.md) en la documentación de implementación. Por ejemplo, este comando agrega a todos los usuarios de NorthAmericaUsers OU del Directorio activo al salón de chat NorthAmerica:

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

Su comando agrega a todos los miembros del grupo de distribución Financias al mismo salón de chat:

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

