---
title: Preguntas más frecuentes para la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype para profesionales de 2015 herramienta de esfuerzo y rendimiento preguntas más frecuentes (P+F), útiles para averiguar qué configuraciones de la herramienta son compatibles, solución de problemas de la herramienta y clarificar comportamientos que puede ver al que ejecute las herramientas de esfuerzo y rendimiento .
ms.openlocfilehash: f71ff02d1bcb6bb858aa4e00144e55bf43c4cbd5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873453"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Preguntas más frecuentes para la Skype para Business Server 2015 herramienta de esfuerzo y rendimiento
 
Skype para profesionales de 2015 herramienta de esfuerzo y rendimiento preguntas más frecuentes (P+F), útiles para averiguar qué configuraciones de la herramienta son compatibles, solución de problemas de la herramienta y clarificar comportamientos que puede ver al que ejecute las herramientas de esfuerzo y rendimiento .
  
 Estas preguntas más frecuentes describen algunas de las preguntas más frecuentes sobre la Skype para Business Server 2015 Stress and Performance tool y pueden ayudar a con las opciones de configuración de solución de problemas y la herramienta.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>¿Puedo ejecutar LyncPerfTool.exe en producción?

Esto **no** se recomienda. La herramienta afectaría a la experiencia del usuario final, seguridad y rendimiento de su servidor de producción.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Sesión Mis usuarios por primera vez. ¿Por qué mis servidores están ejecutando una carga alta?

La primera vez que los usuarios iniciar sesión, operaciones adicionales que se producen en segundo plano. Como resultado, puede disminuir el rendimiento en el Microsoft SQL Server servidor Back-End. Se recomienda que ejecute una prueba breve que registra en todos los usuarios y, a continuación, reiniciar a los clientes antes de comenzar a medir los resultados con la herramienta. Skype para Business Server no admite más de 12 sesiones de inicio de sesión de usuario simultáneos por segundo, pero por favor, tenga en cuenta el número real que se puede controlar mediante los servidores depende de la configuración del hardware y puede ser menor que el valor admitido.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>¡Mis clientes se están quedando sin memoria! ¿Qué debo hacer?

Si los clientes se están quedando sin memoria, debe reducir el número de usuarios que han iniciado por Skype para grupo de negocio de servidor Front-End. También puede elegir escalar desprotección Front-End pools si el problema es persistente.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>¿Puedo ejecutar esta herramienta en una Skype para Business server, sí?

No debería hacerlo. En este escenario no es compatible porque puede producir un error debido a un error de coincidencia binario y también debido a que el objetivo es medir el consumo de recursos en el servidor. Realmente ejecutando la herramienta existe podría afectar al rendimiento del servidor e invalidar los datos y las medidas.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>¿Puedo ejecutar LyncPerfTool.exe en un servidor Virtual o en Microsoft Hyper-V Server 2008 y 2012?

Sí que se puede.
  
## <a name="what-does-mpop-mean"></a>¿Qué significa MPOP?

MPOP es una forma abreviada de decir "múltiples puntos de presencia". MPOP pretende simular escenarios donde los usuarios inician sesión Skype para cliente empresarial 2015 desde varios equipos o dispositivos. Tenga en cuenta que, en LyncPerfTool.exe, cada extremo usa el perfil predeterminado. En otras palabras, el perfil no se reparten entre dos puntos de presencia.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Ha iniciado LyncPerfTool.exe pero no sucede nada. ¿Qué pasa?

Compruebe el contador Total extremos activo en los servidores para ver si los usuarios se conectan. Si no se conectan a los usuarios, compruebe su Skype para la configuración de Business Server 2015. El problema que esté viendo normalmente se produce debido a que uno de nombre de servidor, prefijo de usuario o contraseña, es incorrecto. Tenga en cuenta que los clientes externos deben especificar los valores de Proxy de acceso y el servidor de destino. Compruebe el número de puerto en el archivo de configuración.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>¿Cómo puedo asegurarme de que se está midiendo algo?

Hay LyncPerfTool los contadores de rendimiento que indican si los usuarios se conectan y realizar acciones, pero la forma más sencilla para asegurarse de que se está midiendo acciones es inicie sesión en una de las cuentas con un Skype para cliente empresarial 2015 y siga los procedimientos acciones usted mismo. Compruebe los resultados para confirmar las medidas tomados.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Tener instaladas las herramientas de herramientas de planeación de capacidad de Lync Server 2010 o planificación de la capacidad de Lync Server 2013. ¿Es correcto?

 ¡Estas herramientas tienen problemas de interoperabilidad! Debe desinstalar todas las versiones anteriores de estas herramientas para obtener datos válidos desde el Skype para Business Server 2015 Stress y la herramienta de rendimiento.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>¿Va a configurar las herramientas de esfuerzo y rendimiento de la topología de servidor de información de llamadas CAA?

No, las herramientas no hacerlo. Las herramientas sólo crean los usuarios, contactos y listas de distribución, para simular la carga de usuarios.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>¿Qué es el número máximo de usuarios que admiten las herramientas?

En las pruebas, hemos creado hasta un total de 80.000 usuarios y ejecuta las pruebas por un total de 30.000 usuarios que ejecute estas herramientas. Se recomienda un máximo de 120.000 usuarios, aunque las limitaciones técnicas permiten para los valores más altos. Recuerde que estos valores dependen del servidor y el hardware en su entorno.
  

