---
title: Informe de registro de usuario en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Resumen: Obtenga información sobre el informe de registro de usuario en Skype empresarial Server.'
ms.openlocfilehash: efdb701a61f527e3dd56c1f1e0662f3f1b7f0f8b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279672"
---
# <a name="user-registration-report-in-skype-for-business-server"></a>Informe de registro de usuario en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre el informe de registro de usuario en Skype empresarial Server.
  
El informe de registro de usuario proporciona una descripción general de la actividad de inicio de sesión de usuario, principalmente información sobre el número de usuarios que han iniciado sesión en Skype empresarial Server durante un período de tiempo específico (cada hora, diariamente, semanalmente, mensualmente). Tenga en cuenta que el informe solo indica cuántas personas han iniciado sesión. No indica qué personas iniciaron sesión. Los informes de supervisión no proporcionan información sobre qué usuarios específicos usan Skype empresarial Server (y cuáles no). Pero, puede usar el Informe de actividad de usuario para obtener una estimación de la información de usuarios.
  
Al proporcionar información sobre el inicio de sesión de los usuarios, el Informe de registro de usuario hace dos distinciones. En primer lugar, desglosa los inicios de sesión en dos categorías: inicios de sesión internos y externos. Los inicios de sesión internos corresponden a usuarios que iniciaron sesión desde dentro del firewall de la organización (es decir, mientras estaban conectados a la red corporativa). Los inicios de sesión externos representan a los usuarios que iniciaron sesión desde fuera del Firewall a través de un servidor perimetral (por ejemplo, un usuario que inició sesión desde un café de Internet cuenta como un inicio de sesión externo). Puede usar el Informe de registro de usuario para saber cuántos de sus usuarios han iniciado sesión desde fuera del firewall.
  
Además, el Informe de registro de usuario indica el número de usuarios activos presentes en un periodo determinado. Un usuario activo es un usuario que participó en una sesión de mensajería instantánea (mi), participó en una reunión de Skype empresarial Server, realizó o recibió una llamada de teléfono o, de otro modo, uso de Skype empresarial Server durante ese período de tiempo. No tienen que confundirse este tipo de usuario con los usuarios que hayan iniciado sesión y que nunca hayan usado el sistema.
  
## <a name="accessing-the-user-registration-report"></a>Acceso al Informe de registro de usuario

Puede tener acceso al Informe de registros de usuario únicamente desde la página de inicio de los informes de supervisión. El Informe de registro de usuario no está vinculado a ningún otro informe.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Cómo sacar el máximo partido al Informe de registro de usuario

Una vez que haya implementado Skype empresarial Server, una de las preguntas más frecuentes es la siguiente: ¿Cómo sé si mis usuarios usan realmente esta nueva tecnología? Aunque existen algunas limitaciones al respecto, el Informe de registro de usuario puede ayudarle a encontrar una respuesta para esta pregunta. Para determinar si los usuarios usan Skype empresarial Server, debe hacer dos cosas. En primer lugar, tendrá que obtener el valor de la métrica Usuarios de inicios de sesión distintos del Informe de registro de usuario. Este valor indica cuántas personas distintas han iniciado sesión en Skype empresarial Server.
  
Por comparación, el número total de inicios de sesión métrico muestra cuántas horas totales han iniciado sesión en Skype empresarial Server. Por ejemplo, supongamos que Ken Myer ha iniciado sesión en Skype empresarial Server cinco veces diferentes en un solo día. En ese caso, Ken Myer podría contar con cinco sesiones de inicio de sesión distintas para el total de inicios de sesión, pero solo un usuario de inicio de sesión para la métrica de usuarios de inicio de sesión únicos. Del mismo modo, no es raro que un usuario inicie sesión desde varios dispositivos o desde varias ubicaciones. Por ejemplo, un usuario puede iniciar sesión con su equipo de escritorio, su equipo portátil, y puede tener un teléfono IP que inicie sesión automáticamente en Skype empresarial Server. En este ejemplo, hay un usuario único con tres inicios de sesión.
  
Para explicar la diferencia entre inicios de sesión únicos y totales, es necesario considerar los inicios de sesión que se producen durante un periodo determinado en la tabla siguiente.
  
|**Usuario**|**Hora de inicio de sesión**|
|:-----|:-----|
|Ken Myer  <br/> |07/07/2015 08:45  <br/> |
|Ken Myer  <br/> |07/07/2015 8:46  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 9:17  <br/> |
|Ken Myer  <br/> |07/07/2015 9:22  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 9:31  <br/> |
   
Tenga en cuenta que existe un total de cinco inicios de sesión. Pero, solo hay dos inicios de sesión únicos: Ken Myer (que ha iniciado sesión tres veces) y Pilar Ackerman (que ha iniciado sesión dos veces). Esa es la diferencia entre inicios de sesión y usuario de inicios de sesión distinto.
  
Además de conocer el número de inicios de sesión únicos, necesita saber el número total de usuarios que se han habilitado para Skype empresarial Server. Ese valor se puede recuperar abriendo el shell de administración de Skype empresarial Server y ejecutando el siguiente comando de Windows PowerShell:
  
```
(Get-CsUser).Count
```

Si el comando anterior devuelve un valor de 1.236 y el inicio de sesión único métrica de usuarios devuelve un valor promedio de 667, lo que indica que un poco más de la mitad de los usuarios habilitan realmente el inicio de sesión en el sistema cada día (es decir, , 667 dividida por 1.236, que es aproximadamente un 54%.
  
> [!CAUTION]
> Es necesario tener en cuenta que las métricas de inicio de sesión registran los usuarios que han iniciado sesión durante el periodo especificado. Estas métricas no registran los usuarios que ya habían iniciado sesión en el sistema. Por ejemplo, si la métrica de Usuarios de inicios de sesión distintos muestra 667 inicios de sesión y tiene 1236 usuarios, quiere decir que aproximadamente la mitad de los usuarios han iniciado sesión en el sistema. Pero, suponga que 300 usuarios ya habían iniciado sesión en el sistema en el momento en que comenzó a comprobar los datos de inicio de sesión. Eso significa que en realidad tenía casi 1.000 usuarios que iniciaron sesión en Skype empresarial Server, lo cual significa que cerca de 80% de los usuarios iniciaron sesión. 
  
También es necesario comparar el valor de Usuarios de inicios de sesión distintos con el valor de la métrica Usuarios activos distintos. La métrica usuarios activos únicos le indica cuántos usuarios únicos han usado realmente Skype empresarial Server: hicieron una llamada telefónica, se unieron a una reunión de Skype empresarial Server o participaron en una sesión de mensajería instantánea. Esta información es útil, ya que Skype empresarial Server se puede configurar para que se inicie automáticamente cada vez que un usuario inicie Windows. Por eso, es posible que tenga un gran número de usuarios que inician sesión automáticamente en Skype empresarial cuando inician sesión en Windows cada día, pero, en realidad, nunca usan Skype empresarial Server durante ese período de tiempo.
  
La métrica usuarios únicos activos también proporciona datos más significativos en una organización en la que los usuarios normalmente no cierran la sesión de Windows al final del día. En su lugar, simplemente bloquean sus equipos y dejan Windows y Skype empresarial. En esta situación, puede registrar muy pocos inicios de sesión al día porque los usuarios simplemente iniciaron sesión hace varios días y aún mantienen la sesión iniciada. Sin embargo, los usuarios activos únicos le indican si los usuarios usan activamente Skype empresarial u otro cliente de Skype empresarial Server.
  
## <a name="filters"></a>Filtros

Los filtros ofrecen el medio para devolver un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de registro de usuario le permite ver los datos de todos los grupos de registradores y servidores perimetrales o ver los datos de un grupo individual. También se puede elegir cómo agrupar los datos. En este caso, los registros se agrupan por hora, día, semana o mes.
  
En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de registro de usuario.
  
**Filtros del informe de registro de usuario**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 07/07/2015 y una fecha de finalización del 28/02/2015, aparecerán los datos correspondientes a los días entre el 07/08/2015 a las 12:00 horas y el 07/09/2015 a las 12:00 horas (es decir, datos para un total de 31 días). <br/> |
|**Grupo de servidores** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo de servidores individual o elegir **[Todos]** para ver los datos de todos los grupos de servidores. Esta lista desplegable se rellena automáticamente con los registros de la base de datos. <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente, se muestra la información proporcionada en el informe de registro de usuario. 
  
**Métricas del informe de registro de usuario**

|**Nombre.**|**¿Se pueden ordenar los datos por este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Cada hora** <br/> **Cada día** <br/> **Cada semana** <br/> **Cada mes** <br/> |No  <br/> |Indica el intervalo temporal que ha seleccionado en la barra de herramientas para filtros. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si está usando el intervalo de Cada día y hace clic en 07/07/2015, verá un desglose por horas de la actividad de registro del usuario correspondiente para esa fecha.  <br/> |
|**Total de inicios de sesión** <br/> |No  <br/> |Cantidad total de sesiones de inicio correctas.  <br/> |
|**Inicios de sesión internos** <br/> |No  <br/> |Cantidad total de inicios de sesión en la red interna.  <br/> |
|**Inicios de sesión externos** <br/> |No  <br/> |Cantidad total de inicios de sesión realizados desde fuera de la red interna, por medio del servidor perimetral.  <br/> |
|**Usuarios de inicios de sesión únicos** <br/> |No  <br/> |Cantidad total de usuarios con al menos una sesión de inicio. Un usuario con varias sesiones de inicio se considera un usuario, al igual que una persona con una sola sesión de inicio.  <br/> |
|**Usuarios activos únicos** <br/> |No  <br/> |Cantidad total de usuarios que participaron en una sesión punto a punto o de conferencia. Un usuario con varias sesiones se considera un usuario, al igual que una persona con una sola sesión.  <br/> |
   

