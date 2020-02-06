---
title: Preguntas más frecuentes sobre la herramienta de estrés y rendimiento de Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Preguntas más frecuentes (p + f) sobre la herramienta de estrés y rendimiento de Skype empresarial 2015, útil para descubrir qué configuraciones de herramientas son compatibles, problemas de herramientas de solución de problemas y clarificar comportamientos que puede ver al ejecutar las herramientas de estrés y rendimiento .
ms.openlocfilehash: 2847ecd54389f64d6961cc72ecb94d87e847b0b0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816189"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Preguntas más frecuentes sobre la herramienta de estrés y rendimiento de Skype empresarial Server 2015
 
Preguntas más frecuentes (p + f) sobre la herramienta de estrés y rendimiento de Skype empresarial 2015, útil para descubrir qué configuraciones de herramientas son compatibles, problemas de herramientas de solución de problemas y clarificar comportamientos que puede ver al ejecutar las herramientas de estrés y rendimiento .
  
 Esta pregunta frecuente cubre algunas de las preguntas más frecuentes sobre la herramienta de estrés y rendimiento de Skype empresarial Server 2015, y puede ayudarle con la solución de problemas y las opciones de configuración de herramientas.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>¿Puedo ejecutar LyncPerfTool. exe en producción?

Esto **no** es recomendable. La herramienta afectaría al rendimiento, la seguridad y la experiencia del usuario final de su servidor de producción.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Estoy registrando a mis usuarios por primera vez. ¿Por qué los servidores ejecutan una carga alta?

La primera vez que los usuarios inician sesión, se realizan operaciones adicionales en segundo plano. Como resultado, se puede degradar el rendimiento en el servidor de back-end de Microsoft SQL Server. Se recomienda ejecutar una prueba breve que inicie sesión en todos los usuarios y, a continuación, reiniciar los clientes antes de empezar a medir los resultados con la herramienta. Skype empresarial Server no admite más de 12 sesiones de inicio de sesión de usuario simultáneas por segundo, pero ten en cuenta que el número real que pueden controlar los servidores depende de tu configuración de hardware y puede ser inferior al valor admitido.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Mis clientes se están quedando sin memoria. ¿Qué debo hacer?

Si los clientes se están quedando sin memoria, debe reducir el número de usuarios que han iniciado sesión en el grupo de servidores front-end de Skype empresarial Server. También puede optar por escalar las agrupaciones frontales si el problema es persistente.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>¿Puedo ejecutar esta herramienta en un servidor de Skype para empresas?

No debes hacerlo. Este escenario no es compatible porque puede producirse un error de coincidencia binaria, y también porque el objetivo es medir el consumo de recursos en el servidor. En realidad, ejecutar la herramienta afectaría al rendimiento del servidor e invalidar los datos y las medidas.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>¿Puedo ejecutar LyncPerfTool. exe en un servidor virtual o en Microsoft Hyper-V Server 2008/2012?

Sí, puede hacerlo.
  
## <a name="what-does-mpop-mean"></a>¿Qué significa MPOP?

MPOP es una forma abreviada de decir "varios puntos de presencia". MPOP está pensado para simular escenarios en los que los usuarios inician sesión en el cliente de Skype empresarial 2015 desde varios equipos o dispositivos. Tenga en cuenta que, en LyncPerfTool. exe, cada extremo usa el perfil predeterminado. En otras palabras, el perfil no se divide entre dos puntos de presencia.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Comencé LyncPerfTool. exe, pero no sucede nada. ¿Qué pasa?

Compruebe el contador de extremos activos totales de los servidores para ver si los usuarios se conectan. Si los usuarios no se conectan, verifique su configuración de 2015 de Skype empresarial Server. El problema suele ocurrir porque uno de los nombres de los servidores, el prefijo de usuario o la contraseña son incorrectos. Tenga en cuenta que los clientes externos deberían especificar valores de proxy de acceso y TargetServer. Compruebe el número de puerto en el archivo de configuración.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>¿Cómo puedo estar seguro de que se está midiendo algo?

Hay contadores de rendimiento de LyncPerfTool que indican si los usuarios están conectados o no, pero la manera más sencilla de asegurarse de que las acciones se están midiendo es iniciar sesión en una de las cuentas con un cliente de Skype empresarial 2015 y hacer lo mismo acciones usted mismo. Compruebe los resultados para confirmar que se han realizado medidas.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Tengo instaladas las herramientas de planeación de capacidad de Lync Server 2010 o las herramientas de planeación de capacidad de Lync Server 2013. ¿Está bien?

 Estas herramientas tienen problemas de interoperabilidad. Debe desinstalar todas las versiones anteriores de estas herramientas para obtener datos válidos de la herramienta de estrés y rendimiento de Skype empresarial Server 2015.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>¿Configuran las herramientas de estrés y rendimiento la topología de servidor de información de llamadas de CAA?

No, las herramientas no funcionarán. Las herramientas solo crean usuarios, contactos y listas de distribución para simular la carga de usuarios.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>¿Cuál es el número máximo de usuarios que admiten las herramientas?

En las pruebas, hemos creado hasta un total de 80.000 usuarios y hemos ejecutado pruebas que suman a 30.000 usuarios que ejecutan estas herramientas. Sugerimos un máximo de 120.000 usuarios, aunque las limitaciones técnicas permiten un valor superior. Recuerde que estos valores dependen del servidor y del hardware de su entorno.
  

