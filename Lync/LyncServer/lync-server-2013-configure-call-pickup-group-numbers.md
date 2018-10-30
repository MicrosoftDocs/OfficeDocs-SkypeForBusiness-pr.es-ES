---
title: Configurar los números de grupo de respuesta de llamadas
TOCTitle: Configurar los números de grupo de respuesta de llamadas
ms:assetid: 5cc67f0b-d70d-446a-8db1-befda8671121
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945631(v=OCS.15)
ms:contentKeyID: 52061645
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar los números de grupo de respuesta de llamadas

 

_**Última modificación del tema:** 2013-01-30_

La atención de llamadas grupales se basa en el Aplicación de estacionamiento de llamadas. Al implementar la atención de llamadas grupales, debe configurar la tabla de órbitas de estacionamiento de llamadas con intervalos de números de teléfono que se designan como números del grupo de atención de llamadas. Estos números del grupo son los números que marcan los usuarios para atender llamadas que suenan para otros usuarios.

Al igual que los números de órbita de estacionamiento de llamadas, los números del grupo de atención de llamadas deben ser extensiones virtuales que no tengan asignado ningún usuario o teléfono. Cada grupo de servidores front-end donde implementa la atención de llamadas grupales puede tener uno o más intervalos de números del grupo de atención de llamadas. Los intervalos de números del grupo deben ser globalmente únicos en toda la implementación de Lync Server.

## En esta sección

[Crear o modificar un intervalo numérico de respuesta de llamadas en grupo](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

