---
title: Preguntas más frecuentes sobre la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Preguntas más frecuentes (P+F) de la Herramienta de esfuerzo y rendimiento de Skype Empresarial 2015, útiles para averiguar qué configuraciones de herramientas se admiten, solucionar problemas de las herramientas y aclarar comportamientos que puede ver al ejecutar las herramientas de esfuerzo y rendimiento.
ms.openlocfilehash: 4c9a8acca21e4e4bb8f6b6e0a5ff1f68484e6b1c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814970"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Preguntas más frecuentes sobre la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015
 
Preguntas más frecuentes (P+F) de la Herramienta de esfuerzo y rendimiento de Skype Empresarial 2015, útiles para averiguar qué configuraciones de herramientas se admiten, solucionar problemas de las herramientas y aclarar comportamientos que puede ver al ejecutar las herramientas de esfuerzo y rendimiento.
  
 En estas preguntas más frecuentes se tratan algunas de las preguntas más frecuentes sobre la herramienta Stress and Performance de Skype Empresarial Server 2015, y pueden ayudar con la solución de problemas y las opciones de configuración de herramientas.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>¿Puedo ejecutar LyncPerfTool.exe en producción?

Esto no **se** recomienda. La herramienta afectaría al rendimiento, la seguridad y la experiencia del usuario final del servidor de producción.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Estoy iniciando sesión de mis usuarios por primera vez. ¿Por qué mis servidores ejecutan una carga elevada?

La primera vez que los usuarios inician sesión, se producen operaciones adicionales en segundo plano. Como resultado, se puede degradar el rendimiento Microsoft SQL Server servidor back-end. Se recomienda ejecutar una prueba breve que inicie sesión en todos los usuarios y, a continuación, reiniciar los clientes antes de empezar a medir los resultados con la herramienta. Skype Empresarial Server no admite más de 12 sesiones simultáneas de inicio de sesión de usuario por segundo, pero tenga en cuenta que el número real que pueden controlar los servidores depende de la configuración de hardware y puede ser inferior al valor admitido.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Mis clientes se están quedando sin memoria. ¿Qué tengo que hacer?

Si los clientes se están quedando sin memoria, debe reducir el número de usuarios que han iniciado sesión por grupo de servidores front-end de Skype Empresarial Server. También puede elegir escalar horizontalmente grupos de servidores front-end si el problema es persistente.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>¿Puedo ejecutar esta herramienta en un servidor de Skype Empresarial?

No debes hacerlo. Este escenario no se admite porque puede producir un error debido a un error de coincidencia binaria y también porque el objetivo es medir el consumo de recursos en el servidor. En realidad, ejecutar la herramienta allí afectaría al rendimiento del servidor e invalidaría los datos y las medidas.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>¿Puedo ejecutar LyncPerfTool.exe en un servidor virtual o en Microsoft Hyper-V Server 2008/2012?

Sí, puede hacerlo.
  
## <a name="what-does-mpop-mean"></a>¿Qué significa MPOP?

MPOP es una forma abreviada de decir "varios puntos de presencia". MPOP está diseñado para simular escenarios en los que los usuarios han iniciado sesión en el cliente de Skype Empresarial 2015 desde varios equipos o dispositivos. Tenga en cuenta que, en LyncPerfTool.exe, cada extremo usa el perfil predeterminado. En otras palabras, el perfil no está dividido entre dos puntos de presencia.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Com com LyncPerfTool.exe pero no sucede nada. ¿Qué sucede?

Compruebe el contador Total de extremos activos en los servidores para ver si los usuarios se están conectando. Si los usuarios no se conectan, compruebe la configuración de Skype Empresarial Server 2015. El problema que ve normalmente se produce porque uno de los nombres de servidor, prefijo de usuario o contraseña es incorrecto. Tenga en cuenta que los clientes externos deben especificar valores de Proxy de acceso y TargetServer. Compruebe el número de puerto en el archivo de configuración.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>¿Cómo puedo estar seguro de que se está midendo algo?

Hay contadores de rendimiento de LyncPerfTool que indican si los usuarios se conectan y realizan acciones, pero la forma más sencilla de asegurarse de que se miden las acciones es iniciar sesión en una de las cuentas con un cliente de Skype Empresarial 2015 y realizar esas acciones usted mismo. Compruebe los resultados para confirmar que se han tomado medidas.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Tengo instaladas las herramientas de planeación de capacidad de Lync Server 2010 o las herramientas de planeación de capacidad de Lync Server 2013. ¿Está bien?

 Estas herramientas tienen problemas de interoperabilidad. Debe desinstalar todas las versiones anteriores de estas herramientas para obtener datos válidos de la herramienta Stress and Performance de Skype Empresarial Server 2015.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>¿Las herramientas de esfuerzo y rendimiento configurarán la topología del servidor de información de llamadas CAA?

No, las herramientas no lo hacen. Las herramientas solo crean usuarios, contactos y listas de distribución para simular la carga de usuarios.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>¿Cuál es el número máximo de usuarios que admiten las herramientas?

En las pruebas, hemos creado un total de 80.000 usuarios y hemos ejecutado pruebas que suman un total de 30.000 usuarios que ejecutan estas herramientas. Se recomienda un máximo de 120.000 usuarios, aunque las limitaciones técnicas permiten valores superiores. Recuerde que estos valores dependen del servidor y del hardware de su entorno.
  

