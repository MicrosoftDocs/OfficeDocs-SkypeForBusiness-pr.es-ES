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
ms.openlocfilehash: de9e16a7977a077dd40aaae30f39e11f65ca7c23
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a>Ejecución de transacciones sintéticas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-18_

Las transacciones sintéticas se suelen llevar a cabo de dos maneras. Puede usar los cmdlets CsHealthMonitoringConfiguration para configurar los usuarios de prueba para cada uno de sus grupos de registradores. Estos usuarios de prueba son un par de usuarios que estaban preconfigurados para su uso con transacciones sintéticas. (Normalmente, son cuentas de prueba y no cuentas que pertenecen a usuarios reales). Con los usuarios de prueba configurados para un grupo de servidores, puede ejecutar una transacción sintética en ese grupo sin tener que especificar las identidades de (y proporcionar las credenciales para) las cuentas de usuario implicadas en la prueba.

O bien, puede ejecutar una transacción sintética con cuentas de usuario reales. Por ejemplo, si dos usuarios no pueden intercambiar mensajes instantáneos, podría ejecutar una transacción sintética con estas dos cuentas de usuario (en lugar de un par de cuentas de prueba) y, a continuación, intentar diagnosticar y resolver el problema. Si decide realizar una transacción sintética con cuentas de usuario reales, debe proporcionar los nombres de inicio de sesión y las contraseñas para cada usuario.

<div>

## <a name="see-also"></a>Vea también


[Configuración de usuarios y opciones de configuración de prueba de nodos de monitor en Lync Server 2013](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Instrucciones de configuración especiales para transacciones sintéticas en Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

