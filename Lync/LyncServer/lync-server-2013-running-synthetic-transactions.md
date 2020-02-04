---
title: 'Lync Server 2013: ejecución de transacciones sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b77593ea062f83352592ebe32dbb81b99c1a9613
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a>Ejecución de transacciones sintéticas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-18_

Las transacciones sintéticas se suelen realizar de dos maneras. Puede usar los cmdlets de CsHealthMonitoringConfiguration para configurar los usuarios de prueba para cada uno de sus grupos de registradores. Estos usuarios de prueba son un par de usuarios que estaban preconfigurados para su uso con transacciones sintéticas. (Normalmente, son cuentas de prueba y no cuentas que pertenecen a usuarios reales). Con los usuarios de prueba configurados para un grupo, puede ejecutar una transacción sintética en ese grupo sin necesidad de especificar las identidades de las cuentas de usuario implicadas en la prueba (y proporcionar las credenciales de las mismas).

O bien, puede ejecutar una transacción sintética con cuentas de usuario reales. Por ejemplo, si dos usuarios no pueden intercambiar mensajes instantáneos, podría ejecutar una transacción sintética con esas dos cuentas de usuario (en lugar de un par de cuentas de prueba) y, a continuación, intentar diagnosticar y resolver el problema. Si decide realizar una transacción sintética con cuentas de usuario reales, debe proporcionar los nombres de inicio de sesión y las contraseñas de cada usuario.

<div>

## <a name="see-also"></a>Vea también


[Configuración de los usuarios de prueba y la configuración de los nodos de monitor en Lync Server 2013](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Instrucciones especiales de configuración para transacciones sintéticas en Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

