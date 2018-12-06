---
title: Escenario de migración estándar - Alto nivel
TOCTitle: Escenario de migración estándar - Alto nivel
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48277005
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Escenario de migración estándar - Alto nivel

 

_**Última modificación del tema:** 2013-01-30_

Use los elementos siguientes como punto de partida cuando migre Lync Server 2010, chat en grupo o Office Communications Server 2007 R2Chat en grupo a Lync Server 2013, Servidor de chat persistente. La ruta de migración de Lync Server 2013 estándar es la siguiente:

  - La organización ha implementado previamente Lync Server 2010, chat en grupo o Office Communications Server 2007 R2Chat en grupo y desea implementar Lync Server 2013, Servidor de chat persistente.

  - Implemente Lync Server 2013 y después implemente Grupo de servidores de chat persistente.

  - Prepare y planee la migración de los salones de Chat persistente y determine una hora adecuada para cerrar el sistema a la migración.

  - Ejecute los cmdlets de Windows PowerShell para migración (**Export-CsPersistentChatData** y **Import-CsPersistentChatData**) para mover el contenido a Servidor de chat persistente.

  - Compruebe que la migración se haya efectuado correctamente.

  - Dé de baja la implementación heredada.

  - Configure Servidor de chat persistente para que los clientes heredados puedan conectarse a Lync Server 2013, Servidor de chat persistente. Esto es necesario porque se tarda tiempo en implementar nuevos clientes y probablemente quiera habilitar los usuarios existentes con clientes heredados para que obtengan acceso a sus salones de chat lo más pronto posible.

  - Implemente los clientes nuevos y siga trabajando para asegurarse de que los trabajadores con un Chat en grupo heredado (clientes) puedan tener acceso a sus salones de chat.

