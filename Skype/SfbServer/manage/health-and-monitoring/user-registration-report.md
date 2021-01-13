---
title: Informe de registro de usuarios en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Resumen: obtenga información sobre el informe de registro de usuarios en Skype Empresarial Server.'
ms.openlocfilehash: cb732bdd10c051b35f4f2b69413168fd6515f998
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816650"
---
# <a name="user-registration-report-in-skype-for-business-server"></a>Informe de registro de usuarios en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre el informe de registro de usuarios en Skype Empresarial Server.
  
El informe de registro de usuarios proporciona información general sobre la actividad de inicio de sesión del usuario, especialmente sobre el número de usuarios que iniciaron sesión en Skype Empresarial Server durante un período de tiempo especificado (cada hora, día, semana, mes). Tenga en cuenta que el informe solo indica cuántas personas han iniciado sesión. No indica qué personas iniciaron sesión. Los informes de supervisión no proporcionan información sobre qué usuarios específicos usan Skype Empresarial Server (y cuáles no). Sin embargo, puede usar el Informe de actividad de usuario para obtener una estimación de la información de usuarios.
  
Al proporcionar información sobre el inicio de sesión de los usuarios, el Informe de registro de usuario hace dos distinciones. En primer lugar, desglosa los inicios de sesión en dos categorías: inicios de sesión internos y externos. Los inicios de sesión internos corresponden a usuarios que iniciaron sesión desde dentro del firewall de la organización (es decir, mientras estaban conectados a la red corporativa). Los inicios de sesión externos representan usuarios que iniciaron sesión desde fuera del firewall a través de un servidor perimetral (por ejemplo, un usuario que inició sesión desde un cibercafé cuenta como un inicio de sesión externo). Puede usar el Informe de registro de usuario para saber cuántos de sus usuarios han iniciado sesión desde fuera del firewall.
  
Además, el Informe de registro de usuario indica el número de usuarios activos presentes en un periodo determinado. Un usuario activo es un usuario que participó en una sesión de mensajería instantánea (MI), participó en una reunión de Skype Empresarial Server, realizó o recibió una llamada telefónica o usó Skype Empresarial Server durante ese período de tiempo. No debe confundirse este tipo de usuario con los usuarios que hayan iniciado sesión y que nunca hayan usado el sistema.
  
## <a name="accessing-the-user-registration-report"></a>Acceso al Informe de registro de usuario

Puede tener acceso al Informe de registros de usuario únicamente desde la página de inicio de los informes de supervisión. El Informe de registro de usuario no está vinculado a ningún otro informe.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Cómo sacar el máximo partido al Informe de registro de usuario

Después de implementar Skype Empresarial Server, una de las preguntas más frecuentes es la siguiente: ¿Cómo sé si mis usuarios usan realmente esta nueva tecnología? Aunque existen algunas limitaciones al respecto, el Informe de registro de usuario puede ayudarle a encontrar una respuesta para esta pregunta. Para determinar si los usuarios usan Skype Empresarial Server o no, debe hacer dos cosas. En primer lugar, deberá obtener el valor de la métrica Usuarios de inicios de sesión distintos del Informe de registro de usuario. Este valor le indica cuántas personas distintas iniciaron sesión en Skype Empresarial Server.
  
En comparación, la métrica Inicios de sesión totales muestra cuántas veces se ha iniciado sesión en Skype Empresarial Server. Por ejemplo, supongamos que Ken Myer inició sesión en Skype Empresarial Server cinco veces diferentes en un solo día. En ese caso, Ken Myer contaría como cinco sesiones de inicio de sesión independientes para la métrica Inicios de sesión totales, pero solo un usuario de inicio de sesión para la métrica Usuarios de inicio de sesión únicos. Del mismo modo, no es raro que un usuario inicie sesión desde varios dispositivos o varias ubicaciones. Por ejemplo, un usuario puede iniciar sesión con su equipo de escritorio, su equipo portátil y puede tener un teléfono IP que inicie sesión automáticamente en Skype Empresarial Server. En este ejemplo, hay un usuario único con tres inicios de sesión.
  
Para explicar la diferencia entre inicios de sesión únicos y totales, es necesario considerar los inicios de sesión que se producen durante un periodo determinado en la tabla siguiente.
  
|**Usuario**|**Hora de inicio de sesión**|
|:-----|:-----|
|Ken Myer  <br/> |7/7/2015 8:45 AM  <br/> |
|Ken Myer  <br/> |7/7/2015 8:46 AM  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 9:17 AM  <br/> |
|Ken Myer  <br/> |7/7/2015 9:22 AM  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 9:31 AM  <br/> |
   
Tenga en cuenta que existe un total de cinco inicios de sesión. Sin embargo, solo hay dos inicios de sesión únicos: Ken Myer (que ha iniciado sesión tres veces) y Pilar Ackerman (que ha iniciado sesión dos veces). Esa es la diferencia entre inicios de sesión y usuario de inicios de sesión distinto.
  
Además de conocer el número de inicios de sesión únicos, debe conocer el número total de usuarios habilitados para Skype Empresarial Server. Ese valor se puede recuperar abriendo el Shell de administración de Skype Empresarial Server y ejecutando el siguiente comando Windows PowerShell usuario:
  
```PowerShell
(Get-CsUser).Count
```

Si el comando anterior devuelve un valor de 1.236 y la métrica De usuarios de inicio de sesión único devuelve un valor medio de 667, esto sugiere que algo más de la mitad de los usuarios habilitados para Skype Empresarial inician sesión en el sistema cada día (es decir, 667 dividido por 1.236, que es aproximadamente el 54%).
  
> [!CAUTION]
> Es necesario tener en cuenta que las métricas de inicio de sesión registran los usuarios que han iniciado sesión durante el periodo especificado. Estas métricas no registran los usuarios que ya habían iniciado sesión en el sistema. Por ejemplo, si la métrica de Usuarios de inicios de sesión distintos muestra 667 inicios de sesión y tiene 1.236 usuarios, quiere decir que aproximadamente la mitad de los usuarios han iniciado sesión en el sistema. Sin embargo, suponga que 300 usuarios ya habían iniciado sesión en el sistema en el momento en que comenzó a comprobar los datos de inicio de sesión. Eso significaría que en realidad tenía casi 1.000 usuarios conectados a Skype Empresarial Server, lo que significaría que más cercano al 80 % de los usuarios inició sesión. 
  
También debe comparar el valor de Usuarios de inicios de sesión distintos con el valor de la métrica Usuarios activos distintos. La métrica Usuarios activos únicos le indica cuántos usuarios únicos usaron realmente Skype Empresarial Server: realizaron una llamada telefónica, se unieron a una reunión de Skype Empresarial Server o participaron en una sesión de mensajería instantánea. Esta información es útil, ya que Skype Empresarial Server se puede configurar para iniciarse automáticamente cada vez que un usuario inicia Windows. Por ello, es posible que tenga un gran número de usuarios que inicien sesión automáticamente en Skype Empresarial cuando inicien sesión en Windows cada día, pero que nunca usen Realmente Skype Empresarial Server durante ese período de tiempo.
  
La métrica Usuarios activos únicos también proporciona datos más significativos en una organización en la que los usuarios normalmente no cierran sesión en Windows al final del día. En su lugar, simplemente bloquean sus equipos y dejan windows y Skype Empresarial en ejecución. En esta situación, puede registrar muy pocos inicios de sesión al día porque los usuarios simplemente iniciaron sesión hace varios días y aún mantienen la sesión iniciada. Sin embargo, los usuarios activos únicos le indica si los usuarios usan activamente Skype Empresarial u otro cliente de Skype Empresarial Server.
  
## <a name="filters"></a>Filtros

Los filtros ofrecen el medio para devolver un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de registro de usuarios permite ver los datos de todos los grupos de registradores y servidores perimetrales, o bien ver los datos de un grupo de servidores individual. También se puede elegir cómo agrupar los datos. En este caso, los registros se agrupan por hora, día, semana o mes.
  
En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de registro de usuario.
  
**Filtros del informe de registro de usuario**

|**Nombre**|**Descripción**|
|:-----|:-----|
|**From** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Para** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 7/7/2015 13:00  <br/> Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 7/7/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 7/3/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo de** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solamente se mostrará la cantidad máxima de valores (empezando por la fecha de inicio). Por ejemplo, si selecciona el intervalo diario con una fecha de inicio del 7/7/2015 y una fecha de finalización del 28/2/2015, los datos se muestran para los días 8/7/2015 12:00 AM a 9/7/2015 12:00 AM (es decir, un total de 31 días de datos). <br/> |
|**Grupo** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en **[Todo]** para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos. <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente, se muestra la información proporcionada en el informe de registro de usuario. 
  
**Métricas del informe de registro de usuario**

|**Nombre**|**¿Se pueden ordenar los datos en este elemento?**|**Descripción**|
|:-----|:-----|:-----|
|**Cada hora** <br/> **Diario** <br/> **Semanal** <br/> **Mensualmente** <br/> |No  <br/> |Indica el intervalo temporal que ha seleccionado en la barra de herramientas para filtros. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si usa el intervalo Diario y hace clic en 7/7/2015, verá un desglose por horas de la actividad de registro de usuario para esa fecha.  <br/> |
|**Total de inicios de sesión** <br/> |No  <br/> |Número total de sesiones de inicio correctas.  <br/> |
|**Inicios de sesión internos** <br/> |No  <br/> |Número total de inicios de sesión en la red interna.  <br/> |
|**Inicios de sesión externos** <br/> |No  <br/> |Número total de inicios de sesión realizados desde fuera de la red interna, por medio del servidor perimetral.  <br/> |
|**Usuarios de inicios de sesión distintos** <br/> |No  <br/> |Número total de usuarios con al menos una sesión de inicio. Un usuario con varias sesiones de inicio se considera un usuario, al igual que una persona con una sola sesión de inicio.  <br/> |
|**Usuarios activos distintos** <br/> |No  <br/> |Número total de usuarios que participaron en una sesión punto a punto o de conferencia. Un usuario con varias sesiones se considera un usuario, al igual que una persona con una sola sesión.  <br/> |
   

