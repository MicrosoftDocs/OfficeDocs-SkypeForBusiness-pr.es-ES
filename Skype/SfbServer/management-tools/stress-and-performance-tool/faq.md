---
title: Faq for the Skype Empresarial Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype Empresarial 2015 stress and performance tool frequently asked questions (FAQ), útil para averiguar qué configuraciones de herramientas son compatibles, solucionar problemas de la herramienta y aclarar comportamientos que puede ver al ejecutar las herramientas de esfuerzo y rendimiento.
ms.openlocfilehash: 42fdf53965e190e98e716df0780eac04565d0767
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611939"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Faq for the Skype Empresarial Server 2015 Stress and Performance Tool
 
Skype Empresarial 2015 stress and performance tool frequently asked questions (FAQ), útil para averiguar qué configuraciones de herramientas son compatibles, solucionar problemas de la herramienta y aclarar comportamientos que puede ver al ejecutar las herramientas de esfuerzo y rendimiento.
  
 En esta sección de preguntas más frecuentes se tratan algunas de las preguntas más frecuentes sobre la herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015, y puede ayudar con la solución de problemas y las opciones de configuración de herramientas.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>¿Puedo ejecutar LyncPerfTool.exe en producción?

Esto no **se** recomienda. La herramienta afectaría al rendimiento del servidor de producción, la seguridad y la experiencia del usuario final.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Estoy iniciando sesión en mis usuarios por primera vez. ¿Por qué mis servidores ejecutan una carga alta?

La primera vez que los usuarios inician sesión, se producen operaciones adicionales en segundo plano. Como resultado, el rendimiento en el servidor back-end Microsoft SQL Server puede degradarse. Se recomienda ejecutar una prueba corta que inicie sesión en todos los usuarios y, a continuación, reiniciar los clientes antes de empezar a medir los resultados con la herramienta. Skype Empresarial Server admite más de 12 sesiones de inicio de sesión de usuario simultáneas por segundo, pero tenga en cuenta que el número real que pueden controlar los servidores depende de la configuración de hardware y puede ser inferior al valor admitido.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Mis clientes se están quedando sin memoria. ¿Qué debo hacer?

Si los clientes se están quedando sin memoria, debe reducir el número de usuarios que han iniciado sesión por Skype Empresarial Server grupo de servidores front-end. También puede elegir escalar horizontalmente los grupos de servidores front-end si el problema es persistente.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>¿Puedo ejecutar esta herramienta en un servidor Skype Empresarial, en sí?

No debes hacerlo. Este escenario no se admite porque puede producirse un error debido a una discrepancia binaria y también porque el objetivo es medir el consumo de recursos en el servidor. En realidad, ejecutar la herramienta allí afectaría al rendimiento del servidor e invalidaría los datos y las medidas.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>¿Puedo ejecutar LyncPerfTool.exe un servidor virtual o en Microsoft Hyper-V Server 2008/2012?

Sí se puede.
  
## <a name="what-does-mpop-mean"></a>¿Qué significa MPOP?

MPOP es una forma abreviada de decir "varios puntos de presencia". MPOP está diseñado para simular escenarios en los que los usuarios han iniciado sesión Skype Empresarial cliente de 2015 desde varios dispositivos o máquinas. Tenga en cuenta que, en LyncPerfTool.exe, cada extremo usa el perfil predeterminado. En otras palabras, el perfil no se divide entre dos puntos de presencia.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Comencé a LyncPerfTool.exe pero no está pasando nada. ¿Qué sucede?

Compruebe el contador Extremos activos totales en los servidores para ver si los usuarios se conectan. Si los usuarios no se conectan, compruebe la configuración Skype Empresarial Server 2015. El problema que está viendo suele producirse porque uno de los nombres de servidor, prefijo de usuario o contraseña es incorrecto. Tenga en cuenta que los clientes externos deben especificar valores de Proxy de acceso y TargetServer. Compruebe el número de puerto en el archivo de configuración.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>¿Cómo puedo estar seguro de que algo se está midendo?

Hay contadores de rendimiento de LyncPerfTool que indican si los usuarios se conectan y realizan acciones, pero la forma más sencilla de asegurarse de que se miden las acciones es iniciar sesión en una de las cuentas con un cliente de Skype Empresarial 2015 y realizar esas acciones usted mismo. Compruebe los resultados para confirmar que se han tomado medidas.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Tengo instaladas las Herramientas de planeación de capacidad de Lync Server 2010 o las herramientas de planeación de capacidad de Lync Server 2013. ¿Está bien?

 Estas herramientas tienen problemas de interoperabilidad. Debe desinstalar todas las versiones anteriores de estas herramientas para obtener datos válidos de la herramienta Skype Empresarial Server 2015 Stress and Performance.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>¿Las herramientas de esfuerzo y rendimiento configurarán la topología del servidor de información de llamadas caa?

No, las herramientas no lo hacen. Las herramientas solo crean usuarios, contactos y listas de distribución para simular la carga del usuario.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>¿Cuál es el número máximo de usuarios que admiten las herramientas?

En las pruebas, hemos creado hasta un total de 80.000 usuarios y hemos ejecutado pruebas que suman un total de 30.000 usuarios que ejecutan estas herramientas. Se recomienda un máximo de 120.000 usuarios, aunque las limitaciones técnicas permiten valores más altos. Recuerde que estos valores dependen del servidor y del hardware del entorno.
  

