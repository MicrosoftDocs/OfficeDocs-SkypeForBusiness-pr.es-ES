---
title: 'Lync Server 2013: Implementar el almacenamiento de contactos unificado'
TOCTitle: Implementar el almacenamiento de contactos unificado
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48275562
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar el almacenamiento de contactos unificado en Lync Server 2013

 

_**Última modificación del tema:** 2016-06-06_

Para habilitar el almacén de contactos unificados en Lync Server 2013 no es necesario configurar ninguna topología. Para habilitar el almacén de contactos unificados para los usuarios, se debe cumplir lo siguiente:

  - La directiva de almacén de contactos unificados está habilitada (que es el comportamiento predeterminado).

  - Los usuarios inician sesión con Lync 2013 al menos una vez.

Cuando los contactos de un usuario se hayan migrado (lo que sucede automáticamente cuando dicho usuario inicia sesión con Lync 2013), el usuario podrá acceder a sus contactos de Lync y administrarlos desde Lync 2013, Outlook 2013 o Outlook Web Access. No es necesario haber iniciado sesión en Lync para administrar los contactos desde Outlook o Outlook Web Access.

> [!IMPORTANT]  
> Si un usuario inicia sesión desde Lync 2010 después de la migración, los contactos estarán disponibles y actualizados, pero no se podrán administrar (es decir, agregar, eliminar, mover, modificar, etiquetar o quitar su etiqueta).



## En esta sección

  - [Habilitar usuarios para el almacenamiento de contactos unificado en Lync Server 2013](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [Realizar la migración de usuarios a almacén de contactos unificados en Lync Server 2013](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [Revertir usuarios migrados en Lync Server 2013](lync-server-2013-roll-back-migrated-users.md)

