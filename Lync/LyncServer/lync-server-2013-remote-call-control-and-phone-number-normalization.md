---
title: "Lync Server 2013: Control remoto de llamadas y normalización de números de teléfono"
TOCTitle: Control remoto de llamadas y normalización de números de teléfono
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48274746
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Control remoto de llamadas y normalización de números de teléfono en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-22_

Los clientes de Lync descargan reglas de normalización de números de teléfono como parte de la descarga del archivo del Servicio de libreta de direcciones (ABS). En escenarios de control remoto de llamadas, las reglas de normalización de números de teléfono del Servicio de libreta de direcciones se aplican a las llamadas de control remoto tanto entrantes como realizadas. En el caso de las llamadas entrantes a un usuario habilitado para el control remoto de llamadas, el número de teléfono del autor de la llamada se normaliza en primer lugar al formato E.164, ya sea en la puerta de enlace SIP/CSTA o en la central de conmutación (PBX). Cuando Lync Server 2013 recibe la llamada procedente de la puerta de enlace, lleva a cabo una búsqueda de número inversa (RNL) en el número de teléfono del autor de la llamada con el número normalizado que figura en la lista de contactos de Microsoft Office o en la lista global de direcciones (GAL) del usuario almacenada en el Servicio de libreta de direcciones. En caso de que la búsqueda de número inversa encuentre una coincidencia, el autor de la llamada aparece por su nombre en la notificación de la llamada entrante.

En cuanto a las llamadas de control remoto realizadas, Lync aplica al número marcado las reglas de normalización de números de teléfono del Servicio de libreta de direcciones antes de enrutar la llamada a la puerta de enlace SIP/CSTA.

Para obtener información detallada sobre cómo crear reglas de normalización de números de teléfono para el control remoto de llamadas, vea el tema [Planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) en la documentación de introducción.

## Migración de reglas de normalización de números de teléfono.

Si está migrando usuarios que anteriormente estaban habilitados para el control remoto de llamadas, consulte los siguientes temas en la documentación de migración:

  - Para Lync Server 2010, vea [Migrar libreta de direcciones](migrate-address-book.md) en la documentación de migración.

  - Para Communications Server 2007 R2, vea [Migrar la libreta de direcciones](migrate-address-book_1.md) en la documentación de migración.

