---
title: Preguntas más frecuentes sobre el Skype para Business Server 2015 Stress y la herramienta de rendimiento
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype para la herramienta Business 2015 Stress and Performance preguntas más frecuentes (P+F), útiles para averiguar qué configuraciones de herramienta son compatibles, solución de problemas de la herramienta y clarificar los comportamientos que verá al ejecutar las herramientas de rendimiento y esfuerzo .
ms.openlocfilehash: 730f9620e4aa498df26cc24f3c17ea1bd2ad7d5d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Preguntas más frecuentes sobre el Skype para Business Server 2015 Stress y la herramienta de rendimiento
 
Skype para la herramienta Business 2015 Stress and Performance preguntas más frecuentes (P+F), útiles para averiguar qué configuraciones de herramienta son compatibles, solución de problemas de la herramienta y clarificar los comportamientos que verá al ejecutar las herramientas de rendimiento y esfuerzo .
  
 Estas preguntas frecuentes tratan algunas de las preguntas más frecuentes sobre el Skype para herramientas de 2015 de Business Server Stress and Performance y pueden ayudar con las opciones de configuración de herramienta y solución de problemas.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>¿Puedo ejecutar LyncPerfTool.exe en producción?

Esto **no** es recomendable. La herramienta afectaría la experiencia del usuario final, seguridad y rendimiento de su servidor de producción.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Sesión Mis usuarios por primera vez. ¿Por qué mis servidores están ejecutando una carga alta?

La primera vez que los usuarios iniciar sesión, se producen operaciones adicionales en segundo plano. Como resultado, puede disminuir el rendimiento de Microsoft SQL Server nuevo servidor de fondo. Se recomienda que ejecute una breve prueba que inicie una sesión en todos los usuarios y, a continuación, reiniciar a los clientes antes de comenzar a medir los resultados con la herramienta. Skype para Business Server no admite más de 12 inicios de sesión de usuario simultáneas por segundo, pero ten en cuenta el número real que se puede controlar los servidores depende de la configuración del hardware y puede ser menor que el valor admitido.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>¡Mis clientes están quedando sin memoria! ¿Qué debo hacer?

Si los clientes se están quedando sin memoria, debe reducir el número de usuarios conectados por Skype para el grupo de negocio de servidor Front-End. También puede escalar frente piscinas final si el problema es persistente.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>¿Puedo ejecutar esta herramienta en un Skype para Business server, sí?

No debería hacerlo. Este escenario no es compatible porque puede producir un error debido a una falta de coincidencia binaria y también porque el objetivo es medir el consumo de recursos en el servidor. Realmente ejecutando la herramienta allí podría afectar al rendimiento del servidor e invalidar los datos y las medidas.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>¿Puedo ejecutar LyncPerfTool.exe en un servidor Virtual o en Microsoft Hyper-V Server 2008 y 2012?

Sí se puede.
  
## <a name="what-does-mpop-mean"></a>¿Qué significa MPOP?

MPOP es una forma abreviada de decir "múltiples puntos de presencia". MPOP pretende simular escenarios donde los usuarios inician sesión Skype para cliente de negocios 2015 desde varios equipos o dispositivos. Tenga en cuenta que, en LyncPerfTool.exe, cada extremo utiliza el perfil predeterminado. En otras palabras, el perfil no es dividir entre dos puntos de presencia.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Comencé a LyncPerfTool.exe, pero no sucede nada. ¿Qué pasa?

Compruebe el contador Total extremos activos en los servidores para ver si los usuarios se conectan. Si no se conectan a los usuarios, comprobar su Skype para la configuración de servidor de negocios 2015. El problema que estás viendo, normalmente ocurre porque uno de nombre de servidor, prefijo de usuario o contraseña es incorrecto. Tenga en cuenta que los clientes externos deben especificar los valores de Proxy de acceso y el servidor de destino. Compruebe el número de puerto en el archivo de configuración.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>¿Cómo puedo estar seguro de que se está midiendo algo?

Hay contadores de rendimiento de LyncPerfTool que indican si los usuarios se conectan y realizar acciones, pero es la forma más sencilla de asegurarse de que se está midiendo acciones iniciar sesión en una de las cuentas con un Skype para cliente de negocios 2015 y las acciones usted mismo. Compruebe los resultados para confirmar las medidas tomados.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Tengo instaladas las herramientas de herramientas de planeamiento de capacidad de Lync Server 2010 o Lync Server 2013 Capacity Planning. ¿Es esto correcto?

 ¡Estas herramientas tienen problemas de interoperabilidad! Debe desinstalar todas las versiones anteriores de estas herramientas para obtener datos válidos desde el Skype para Business Server 2015 Stress y la herramienta de rendimiento.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>¿Las herramientas de rendimiento y esfuerzo configurará la topología de servidores de información de llamadas CAA?

No, las herramientas no hacen. Las herramientas sólo crean los usuarios, contactos y listas de distribución, para simular la carga de usuarios.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>¿Cuál es el número máximo de usuarios que las herramientas de soporte?

En las pruebas, hemos creado hasta un total de 80.000 usuarios y ejecutados por un total de 30.000 usuarios ejecutando estas herramientas de pruebas. Se recomienda un máximo de 120.000 usuarios, aunque las limitaciones técnicas permiten los valores más altos. Recuerde que estos valores dependen del servidor y el hardware en su entorno.
  

