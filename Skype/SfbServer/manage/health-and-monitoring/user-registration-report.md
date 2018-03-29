---
title: Informe de registro de usuario en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Resumen: Conozca el informe de registro de usuario en Skype para Business Server 2015.'
ms.openlocfilehash: fcf1640b3d8b87664de060ae5866b830ceea3d3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="user-registration-report-in-skype-for-business-server-2015"></a>Informe de registro de usuario en Skype Empresarial Server 2015
 
**Resumen:** Obtener información sobre el informe de registro de usuario en Skype para Business Server 2015.
  
El informe de registro de usuario proporciona una visión general de la actividad de inicio de sesión de usuario, en especial información acerca del número de usuarios que ha iniciado sesión en Skype para Business Server 2015 durante un período de tiempo especificado (cada hora, diariamente, semanalmente, mensualmente). Tenga en cuenta que el informe solo indica cuántas personas han iniciado sesión. No se indica qué usuarios que iniciaron sesión. Informes de supervisión no proporcionan información que determinados usuarios de Business Server 2015 usando Skype (y cuáles no lo son). Pero, puede usar el Informe de actividad de usuario para obtener una estimación de la información de usuarios.
  
Al proporcionar información sobre el inicio de sesión de los usuarios, el Informe de registro de usuario hace dos distinciones. En primer lugar, desglosa los inicios de sesión en dos categorías: inicios de sesión internos y externos. Los inicios de sesión internos corresponden a usuarios que iniciaron sesión desde dentro del firewall de la organización (es decir, mientras estaban conectados a la red corporativa). Los inicios de sesión externos representan los usuarios que han iniciado sesión fuera del firewall a través de un servidor perimetral (por ejemplo, un usuario que inició sesión desde un Internet café se cuenta como un inicio de sesión externo). Puede usar el Informe de registro de usuario para saber cuántos de sus usuarios han iniciado sesión desde fuera del firewall.
  
Además, el informe de registro de usuario observa cuántos usuarios activos estaban presentes durante un período de tiempo determinado. Un usuario activo es un usuario que formó parte de una sesión (IM), de mensajería instantánea participó en un Skype para Business Server reunión, realizado o recibido una llamada telefónica o lo contrario utiliza Skype para Business Server durante ese período de tiempo. No tienen que confundirse este tipo de usuario con los usuarios que hayan iniciado sesión y que nunca hayan usado el sistema.
  
## <a name="accessing-the-user-registration-report"></a>Acceso al Informe de registro de usuario

Puede tener acceso al Informe de registros de usuario únicamente desde la página de inicio de los informes de supervisión. El Informe de registro de usuario no está vinculado a ningún otro informe.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Cómo sacar el máximo partido al Informe de registro de usuario

Una vez que haya implementado Skype para Business Server uno más frecuentes pregunta es la siguiente: ¿Cómo sé si Mis los usuarios empleen esta nueva tecnología? Aunque existen algunas limitaciones al respecto, el Informe de registro de usuario puede ayudarle a encontrar una respuesta para esta pregunta. Para determinar si los usuarios utilizan Skype para Business Server, debe hacer dos cosas. En primer lugar, tendrá que obtener el valor de la métrica Usuarios de inicios de sesión distintos del Informe de registro de usuario. Este valor indica cuántas personas distintas iniciado sesión en Skype para Business Server.
  
En comparación, la métrica Total de inicios de sesión muestra cuántas veces total que nadie ha iniciado sesión en Skype para Business Server. Por ejemplo, suponga que Ken Myer iniciado sesión en Skype para Business Server cinco veces diferentes en un solo día. En ese caso, Ken Myer contaría como cinco sesiones de inicio de sesión independiente para la métrica Total de inicios de sesión, pero sólo un usuario de inicio de sesión para la métrica de los usuarios de inicio de sesión único. Asimismo, no es raro que un usuario puede iniciar sesión desde varios dispositivos o varias ubicaciones. Por ejemplo, un usuario puede iniciar sesión con su equipo de escritorio, su equipo portátil, y puede tener un teléfono IP que inicie sesión automáticamente en Skype para Business Server. En este ejemplo, hay un único usuario con tres inicios de sesión.
  
Para explicar la diferencia entre inicios de sesión únicos y totales, es necesario considerar los inicios de sesión que se producen durante un periodo determinado en la tabla siguiente.
  
|**Usuario**|**Hora de inicio de sesión**|
|:-----|:-----|
|Ken Myer  <br/> |07/07/2015 08:45  <br/> |
|Ken Myer  <br/> |07/07/2015 8:46  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 9:17  <br/> |
|Ken Myer  <br/> |07/07/2015 9:22  <br/> |
|Pilar Ackerman  <br/> |07/07/2015 9:31  <br/> |
   
Tenga en cuenta que existe un total de cinco inicios de sesión. Pero, solo hay dos inicios de sesión únicos: Ken Myer (que ha iniciado sesión tres veces) y Pilar Ackerman (que ha iniciado sesión dos veces). Esa es la diferencia entre inicios de sesión y usuario de inicios de sesión distinto.
  
Además de saber el número de inicios de sesión únicos, necesitará saber el número total de usuarios que han sido habilitados para Skype para Business Server. Ese valor se puede recuperar abriendo el Skype para el Shell de administración de servidor empresarial y ejecutando el siguiente comando de Windows PowerShell:
  
```
(Get-CsUser).Count
```

Si el comando anterior devuelve un valor de 1,236 y métrica de los usuarios de inicio de sesión único devuelve el valor medio de 667, que sugiere que un poco más de la mitad de sus usuarios habilitar para Skype para empresas se iniciar una sesión en el sistema cada día (es decir 667 dividido por 1,236, que es aproximadamente 54%).
  
> [!CAUTION]
> Es necesario tener en cuenta que las métricas de inicio de sesión registran los usuarios que han iniciado sesión durante el periodo especificado. Estas métricas no registran los usuarios que ya habían iniciado sesión en el sistema. Por ejemplo, si la métrica de Usuarios de inicios de sesión distintos muestra 667 inicios de sesión y tiene 1236 usuarios, quiere decir que aproximadamente la mitad de los usuarios han iniciado sesión en el sistema. Pero, suponga que 300 usuarios ya habían iniciado sesión en el sistema en el momento en que comenzó a comprobar los datos de inicio de sesión. Eso significa que se hayan casi 1.000 usuarios han iniciado sesión Skype para Business Server, lo que significaría que más cerca al 80% de los usuarios se han iniciado sesión. 
  
También es necesario comparar el valor de Usuarios de inicios de sesión distintos con el valor de la métrica Usuarios activos distintos. La métrica de usuarios únicos activos le indica cuántos usuarios únicos realmente usa Skype Business Server: realiza una llamada telefónica, se unieron a un Skype para Business Server reunión o han participado en una sesión de IM. Esta información es útil, porque Skype para Business Server 2015 puede configurarse para que se inicie automáticamente cada vez que un usuario inicia Windows. Por este motivo, podría tener un gran número de usuarios que inicien la sesión automáticamente Skype para el negocio cuando inicie sesión en Windows cada día, pero entonces nunca realmente se utilizan Skype para Business Server durante ese período de tiempo.
  
La métrica de usuarios únicos activos también proporciona los datos más significativos en una organización donde los usuarios normalmente no cerrar sesión Windows al final del día. En su lugar, simplemente bloquear sus equipos y dejar Windows y Skype para el negocio en funcionamiento. En esta situación, puede registrar muy pocos inicios de sesión al día porque los usuarios simplemente iniciaron sesión hace varios días y aún mantienen la sesión iniciada. Sin embargo, usuarios únicos activos indica si los usuarios utilizan activamente Skype para empresa u otro Skype para cliente Business Server.
  
## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de registro de usuario permite ver los datos de todos los servidores perimetrales y grupo de Registrar o ver los datos de un grupo de servidores individual. También se puede elegir cómo agrupar los datos. En este caso, los registros se agrupan por hora, día, semana o mes.
  
En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de registro de usuario.
  
**Filtros de informe de registro de usuario**

|**Nombre.**|**Descripción**|
|:-----|:-----|
|**De** <br/> |Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Hasta** <br/> |Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:  <br/> 07/07/2015 13:00  <br/> Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:  <br/> 07/07/2015  <br/> Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):  <br/> 03/07/2015  <br/> Las semanas siempre van del domingo al sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tiempo. Seleccione una de las siguientes opciones: <br/>  Cada hora (se puede ver un máximo de 25 horas) <br/>  Cada día (se puede ver un máximo de 31 días) <br/>  Cada semana (se puede ver un máximo de 12 semanas) <br/>  Cada mes (se puede ver un máximo de 12 meses) <br/>  Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 07/07/2015 y una fecha de finalización del 28/02/2015, aparecerán los datos correspondientes a los días entre el 07/08/2015 a las 12:00 horas y el 07/09/2015 a las 12:00 horas (es decir, datos para un total de 31 días). <br/> |
|**Grupo de servidores** <br/> |Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo de servidores individual o elegir **[Todos]** para ver los datos de todos los grupos de servidores. Esta lista desplegable se rellena automáticamente con los registros de la base de datos. <br/> |
   
## <a name="metrics"></a>Métricas

En la tabla siguiente, se muestra la información proporcionada en el informe de registro de usuario. 
  
**Métricas de informe de registro de usuario**

|**Nombre.**|**¿Puede ordenar por este artículo?**|**Descripción**|
|:-----|:-----|:-----|
|**Cada hora** <br/> **Cada día** <br/> **Cada semana** <br/> **Cada mes** <br/> |No  <br/> |Indica el intervalo temporal que ha seleccionado en la barra de herramientas para filtros. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si está usando el intervalo de Cada día y hace clic en 07/07/2015, verá un desglose por horas de la actividad de registro del usuario correspondiente para esa fecha.  <br/> |
|**Total de inicios de sesión** <br/> |No  <br/> |Cantidad total de sesiones de inicio correctas.  <br/> |
|**Inicios de sesión internos** <br/> |No  <br/> |Cantidad total de inicios de sesión en la red interna.  <br/> |
|**Inicios de sesión externos** <br/> |No  <br/> |Cantidad total de inicios de sesión realizados desde fuera de la red interna, por medio del servidor perimetral.  <br/> |
|**Usuarios de inicios de sesión únicos** <br/> |No  <br/> |Cantidad total de usuarios con al menos una sesión de inicio. Un usuario con varias sesiones de inicio se considera un usuario, al igual que una persona con una sola sesión de inicio.  <br/> |
|**Usuarios activos únicos** <br/> |No  <br/> |Cantidad total de usuarios que participaron en una sesión punto a punto o de conferencia. Un usuario con varias sesiones se considera un usuario, al igual que una persona con una sola sesión.  <br/> |
   

