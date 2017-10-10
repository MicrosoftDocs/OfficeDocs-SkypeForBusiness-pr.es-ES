---
title: Habilitar Microsoft Teams en paralelo con Skype Empresarial
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Guía para usar Skype Empresarial y Microsoft Teams en paralelo."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 760fa47db7965e0c2a74b01ae25f1d23d37d3180
ms.sourcegitcommit: 2592b268977460d0d483a75d741b1ce9fa8da908
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2017
---
<a name="enable-microsoft-teams-side-by-side-with-skype-for-business"></a>Habilitar Microsoft Teams en paralelo con Skype Empresarial 
=============================================================

Para las organizaciones que tienen implementado actualmente Skype Empresarial Online, la reciente introducción de Microsoft Teams supone una oportunidad para evaluar el potencial de Microsoft Teams como una única solución de colaboración y comunicaciones y un reto para evaluar las dos soluciones y cómo coexisten en su entorno.

Si Microsoft Teams cumple los requisitos de negocio que tiene hoy en día, podrá comenzar a adoptarlo hasta que se convierta en la única solución de colaboración y comunicaciones de su organización.

Microsoft Teams está habilitado de forma predeterminada en todos los inquilinos que reúnen las condiciones. Por lo tanto, tiene que decidir cómo va a administrar Microsoft Teams en paralelo con Skype Empresarial y seguir cumpliendo las expectativas de los usuarios.

En general, hay dos recorridos de cliente en paralelo principales. Son los siguientes:

-   **Opción 1:** recorrido de cliente no administrado en paralelo.

    TI no controla de forma activa la experiencia en paralelo y se autoriza a los usuarios a que elijan la aplicación que prefieren.

-   **Opción 2:** recorrido de cliente administrado en paralelo.

    TI controla la experiencia en paralelo y guía a los usuarios a lo largo del recorrido que se hace para introducir gradualmente Microsoft Teams: primero se introduce un espacio de trabajo de colaboración nuevo basado en chats con chat privado, después las experiencias de reuniones y, por último, las experiencias de llamada de Microsoft Teams.

![](media/guidance_SkypeforBusiness_image1.png)

<a name="side-by-side-benefits-and-considerations"></a>Ventajas y consideraciones en paralelo
----------------------------------------

Cada recorrido tiene ventajas y consideraciones que hay que evaluar a la hora de determinar el camino que se debe ir tomando en función del perfil de su organización. En la tabla siguiente se comparan los recorridos de cliente en paralelo que hay: administrados y no administrados.


<table>
<thead>
<tr class="header">
<th align="left">Rutas de migración</th>
<th align="left">En paralelo no administrado</th>
<th align="left">En paralelo administrado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Perfil de la organización</strong></td>
<td align="left"><ul>
<li>Normalmente, organizaciones pequeñas que no tienen recursos de TI dedicados</li>
<li>TI deja que el usuario decida qué herramientas prefiere para su trabajo</li>
<li>El uso principal de Skype Empresarial es MI/P y reuniones</li>
</ul></td>
<td align="left"><ul><li>Normalmente, organizaciones medianas o grandes</li>
<li>TI quiere controlar el despliegue de las nuevas herramientas con mayor rigurosidad</li>
<li>Mayor adopción de Skype Empresarial en este momento</li>
<li>Red e infraestructura más complejas</li>
<li>Varias ubicaciones</p>
<li>Se prefiere una aplicación con funcionalidades exclusivas de comunicaciones unificadas</li></ul></td>
</tr>
<tr class="even">
<td align="left"><strong>Ventajas</strong></td>
<td align="left"><ul>
<li>Se aprovechan funcionalidades en Microsoft Teams que no están disponibles en Skype Empresarial</li>
<li>Un lugar de trabajo moderno y mejorado dentro de Office 365</li>
<li>Mayor flexibilidad para el usuario</li>
<li>Se habilitan todas las funcionalidades a la vez</li>
</ul></td>
<td align="left"><ul><li>Se aprovechan funcionalidades en Microsoft Teams que no están disponibles en Skype Empresarial</li>
<li>Un lugar de trabajo moderno y mejorado dentro de Office 365</li>
<li>Se minimiza el impacto en la productividad de los usuarios</li>
<li>Se reduce la superposición de funcionalidades</li>
<li>Se simplifica la elección de herramientas en escenarios de comunicaciones unificadas</li>
<li>TI y las empresas pueden habilitar funcionalidades según convenga a la organización</li>
<li>Se controla el ritmo de cambio de los usuarios</li></ul></td>
</tr>
<tr class="odd">
<td align="left"><strong>Consideraciones</strong></td>
<td align="left"><ul>
<li>Varias aplicaciones con funcionalidades similares que se solapan</li>
<li>Aumenta las probabilidades de confundir al usuario, lo que deriva en más llamadas de soporte, informática en la sombra y repercusiones en la productividad</li>
<li>La supervisión y planificación de red debe teniendo en cuenta dos servicios</li>
<li>Se necesitan más esfuerzos inmediatos de administración del cambio: reconocimiento, formación y soporte</li>
<li>Los usuarios pueden experimentar limitaciones en la interoperabilidad entre aplicaciones</li>
</ul></td>
<td align="left"><ul><li>TI mantiene un control granular, desde licencias a experiencias de usuario, que requiere ciclos adicionales de planificación e implementación</li>
<li>La acción y los conocimientos de los usuarios hacen que se deshabiliten determinadas funcionalidades en Microsoft Teams</li>
<li>Los esfuerzos de administración de cambios hacen que se deshabiliten determinadas funcionalidades en Microsoft Teams</li>
<li>La supervisión y planificación de red debe teniendo en cuenta dos servicios</li>
<li>Los usuarios pueden experimentar limitaciones en la interoperabilidad entre aplicaciones</li></ul></td>
</tr>
</tbody>
</table>


<a name="unmanaged-side-by-side-customer-journey"></a>Recorrido de cliente no administrado en paralelo
---------------------------------------


![](media/guidance_SkypeforBusiness_image4.png)

En un recorrido de cliente no administrado en paralelo, Microsoft Teams se presenta como una solución de colaboración (un espacio de trabajo basado en chats, canales, aplicaciones, integración con otras cargas de trabajo de Office 365, etc.) que involucra a software cliente y clientes web en equipos de escritorio (PC o Mac) y dispositivos móviles.


De forma predeterminada, Microsoft Teams tiene funcionalidades que se solapan con las de Skype Empresarial; entre ellas, las llamadas y chats privados y las reuniones programadas. Esto implica que Microsoft Teams proporciona finalmente servicios completos de colaboración y comunicaciones a la organización y, al mismo tiempo, Skype Empresarial ofrece funcionalidades similares.

Microsoft Teams admite la interoperabilidad con usuarios de Skype Empresarial Online. Cuando inicien Microsoft Teams, se les dará la oportunidad de elegir la aplicación de llamadas y chat que prefieren. Si un usuario elige Microsoft Teams como su aplicación preferida y otro usuario no ha instalado Microsoft Teams o elige Skype Empresarial como la aplicación de llamadas y chat que prefiere, podrán seguir chateando y llamándose a través de las funcionalidades de interoperabilidad que forman parte de Microsoft Teams.

Microsoft trata de mejorar constantemente las experiencias de interoperabilidad. Es posible que al principio haya casos en los que la interoperabilidad no cumpla las expectativas del usuario. Como Skype Empresarial sigue estando disponible para todos los usuarios, podrán cambiar a Skype Empresarial cuando se dispongan a usar funcionalidades que aún no puede prestar Microsoft Teams.

Las reuniones programadas de Microsoft Teams es otra de las funcionalidades con las que los usuarios pueden programar reuniones con Microsoft Teams o reuniones con Skype Empresarial. Cada una de ellas tiene sus propias ventajas y, a lo largo del tiempo, cuando la experiencia de reuniones de Microsoft Teams cumpla los requisitos empresariales o supere las funcionalidades de las reuniones de Skype Empresarial, esperamos que los usuarios se vayan pasando poco a poco a las reuniones de Microsoft Teams.

En este recorrido de cliente no administrado en paralelo, prepare a su equipo de asistencia al cliente para que pueda gestionar llamadas de usuarios que tienen problemas con las funcionalidades de interoperabilidad. O, si no, informe a los usuarios de cuándo les conviene elegir reuniones de Microsoft Teams antes que de Skype Empresarial y viceversa.

Este recorrido de cliente en paralelo puede aplicarse en su organización. En ese caso, los usuarios se muestran más receptivos a la naturaleza de la experiencia en paralelo no administrada y la organización permite que los usuarios elijan libremente las herramientas de colaboración y comunicaciones que se adecúan mejor a sus necesidades.

<a name="managed-side-by-side-customer-journey"></a>Recorrido de cliente administrado en paralelo
-------------------------------------

![](media/guidance_SkypeforBusiness_image2.png)

Un recorrido administrado de cliente en paralelo se inicia cuando la organización quiere controlar más la introducción de Microsoft Teams.

-   El **primer paso** de este recorrido consiste en crear un proyecto piloto limitado de Microsoft Teams enfocado en requisitos de colaboración moderna (un espacio de trabajo basado en chats, canales, aplicaciones, integración con otras cargas de trabajo de Office 365, etc.). El chat privado y las reuniones de canal ah hoc de Microsoft Teams están habilitados para que los usuarios del proyecto piloto puedan evaluar las experiencias de chat privado y de reuniones de Microsoft Teams si así lo deciden. Las funcionalidades de llamadas privadas y reuniones programadas de Microsoft Teams no están habilitadas en esta fase. Para comenzar con el piloto, vaya a [Crear un proyecto piloto de Microsoft Teams junto a Skype Empresarial](pilot-essentials.md).
    
-   El **segundo paso** de este recorrido consiste en ampliar el lanzamiento de Microsoft Teams para la colaboración moderna con chat privado a toda la organización. Las reuniones programadas y las llamadas privadas siguen deshabilitadas en Microsoft Teams para reducir la superposición con las funcionalidades de Skype Empresarial.

    En esta fase, tiene que pensar si la aplicación de chat que se marcará como preferida para toda la organización será Microsoft Teams o Skype Empresarial.

    - Si se elige Microsoft Teams, prepare a los usuarios para que identifiquen los primeros retos de interoperabilidad que surgirán cuando se comuniquen con otras partes de la organización.
    
    - Si se elige Skype Empresarial, los chats privados de Microsoft Teams seguirán en Microsoft Teams y los usuarios finales podrán beneficiarse de forma inmediata de la naturaleza multiplataforma persistente de las funcionalidades de chat dentro de Microsoft Teams. Así, podrán seguir usando Skype Empresarial para los chats privados entre usuarios de Skype Empresarial, dentro de la organización y en toda ella.


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Nota</p></td>
<td align="left"><br><br>Por ahora, la opción de elegir la aplicación de chat preferida solo está disponible a nivel de cliente. Habrá que realizar una campaña de formación y adopción para extender la configuración a toda la organización.</td>
</tr>
</thead>
<tbody>
</tbody>
</table>

El **tercer paso** del recorrido de cliente gestionado en paralelo se inicia cuando la organización decide que las funcionalidades y la experiencia de reuniones de Microsoft Teams cumplen todos sus requisitos. Al habilitar las reuniones privadas y de canal en Microsoft Teams, se ofrece a los usuarios opciones para programar reuniones de Microsoft Teams y reuniones de Skype Empresarial. Por lo tanto, se espera que, con el tiempo, los usuarios se vayan pasando naturalmente a las reuniones de Microsoft Teams conforme se le vayan incorporando novedades. Para que el paso de Skype Empresarial a Microsoft Teams se haga correctamente, recomendamos implementar un programa sólido de administración de cambios que incluya formación, soporte y comunicaciones donde se explique lo que aporta Microsoft Teams a los usuarios, con instrucciones claras sobre cómo empezar a usarlo. Aproveche nuestros recursos de [preparación de usuarios](http://aka.ms/UserReadiness) para que le ayuden a diseñar su campaña de reconocimiento.


El **cuarto paso** del recorrido de cliente administrado en paralelo comienza cuando se habilitan las llamadas en Microsoft Teams. Las funcionalidades de interoperabilidad de Microsoft Teams tendrán un gran peso en este paso para garantizar que la experiencia en paralelo se desarrolle sin problemas. Idealmente, para forzar que se use Microsoft Teams para realizar llamadas privadas, Microsoft Teams se establece como la aplicación de llamadas predeterminada. 

Conforme vaya pasando el tiempo, toda la organización podrá confiar únicamente en Microsoft Teams para cumplir los requisitos de colaboración y comunicaciones y continuar con el **quinto paso**. Si desea ver las nuevas características que se incluirán en Microsoft Teams, vea el [Mapa de ruta de Office 365](http://aka.ms/TeamsRoadmap). 

<a name="managing-side-by-side-experience"></a>Administrar la experiencia en paralelo
--------------------------------

Microsoft Teams está habilitado de forma predeterminada en aquellas organizaciones que tienen suscripciones de Office 365 válidas. Si su organización cumple el perfil del recorrido de cliente no administrado en paralelo, recomendados encarecidamente que siga por ese camino para promover una adopción orgánica de Microsoft Teams.

A Microsoft Teams se puede acceder a través de clientes de escritorio con navegadores web modernos que no requieren privilegio de administrador de TI (para la instalación, en este momento solo se aplica a PC) y clientes móviles.

Todas las funcionalidades de Microsoft Teams (llamadas y chats privados, y reuniones ad hoc y programadas) y las aplicaciones están habilitadas de forma predeterminada, de manera que los usuarios pueden probar y usar las funcionalidades que mejor se adaptan a lo que necesitan. La primera vez que se utiliza, Microsoft Teams guía a los usuarios para que elijan su aplicación de llamadas y chat preferida (Microsoft Teams o Skype Empresarial).

En caso de que su organización requiera que las nuevas herramientas, como Microsoft Teams, se deben lanzar siguiendo un proceso más controlado, se pueden tener en cuenta las siguientes opciones para su recorrido de cliente administrado en paralelo. Son estas:

-   Experiencia piloto y lanzamiento de Microsoft Teams para colaboración. Vea [Crear un proyecto piloto de Microsoft Teams junto a Skype Empresarial](pilot-essentials.md).

-   Lanzamiento de Microsoft Teams para reuniones

-   Lanzamiento de Microsoft Teams para llamadas

### <a name="teams-pilot-and-rollout-for-collaboration"></a>Experiencia piloto y lanzamiento de Microsoft Teams para colaboración

En esencia, Microsoft Teams se creó en torno al chat persistente y la integración con Office 365 mediante la mejora de Grupos de Office 365.

Dado que, de forma predeterminada, los usuarios de su organización que tienen una licencia de suscripción a Office 365 apta están habilitado para poder usar Microsoft Teams, se crea una experiencia piloto limitada de Microsoft Teams en la que se deshabilita la licencia de Microsoft Teams de todos los usuarios que no pertenecen a este grupo piloto.

Para centrarse en el lanzamiento de Microsoft Teams como solución de chat privado y colaboración, y reducir la confusión que genera en los usuarios tener varias funcionalidades que se solapan con Skype Empresarial, puede cambiar las siguientes configuraciones en el nivel de inquilino de Office 365. Para cambiar estas configuraciones de Office 365, vea [Configurar Microsoft Teams en su organización de Office 365](Office-365-set-up.md).

<table>
<thead>
<tr class="header">
<th align="left">Sección</th>
<th align="left">Configuración</th>
<th align="left">Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>Llamadas y reuniones</strong></td>
<td align="left"><p>Permitir la programación de reuniones privadas: <strong>Desactivado</strong></p><p>Permitir la programación de reuniones de canal: <strong>Desactivado</strong></p><p>Permitir llamada privada: <strong>Desactivado</strong></p></td>
<td align="left"><p>Al deshabilitar esta opción, los usuarios no podrán programar reuniones privadas.</p><p>Al deshabilitar esta opción, los usuarios no podrán programar reuniones de canal.</p><p>Al deshabilitar esta opción, los usuarios no podrán hacer llamadas privadas (audio y vídeo)</p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Nota</p></td>
<td align="left"><br><br>Debe deshabilitar las llamadas privadas a usuarios profesionales, de empresa e invitados (si el acceso de invitado existe en su organización).</td>
</tr>
</thead>
<tbody>
</tbody>
</table>



Con esta configuración, se les puede mostrar a los usuarios cómo funcionan las reuniones en Microsoft Teams al promover el uso de las reuniones de canal ad hoc y al permitir el uso de la voz, el vídeo y la pantalla compartida como parte de la experiencia de colaboración moderna. Los usuarios finales también se benefician de las funcionalidades de chat privado, multiplataforma y persistencia de Microsoft Teams.

Cuando la experiencia piloto de Microsoft Teams se desarrolla con éxito para el chat privado y la colaboración, se puede seguir con un amplio lanzamiento en toda la organización proporcionando licencias de Microsoft Teams a todos los usuarios.

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Nota</p></td>
<td align="left">Durante el piloto y en la fase dos, cuando se habilita el chat privado, un usuario de Microsoft Teams que chatee con un usuario de Skype Empresarial no podrá hacer lo siguiente:<br>
- Iniciar videollamada desde una sesión de chat<br>
- Transferir archivos <br>
- Iniciar una llamada con varios participantes desde la sesión de chat<br>
- Los usuarios no podrán iniciar una sesión de escritorio compartido<br>

</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


### <a name="rollout-of-teams-for-meetings"></a>Lanzamiento de Microsoft Teams para reuniones

A medida que los usuarios se vayan acostumbrando a colaborar con Microsoft Teams, se considerará a las reuniones programadas como la siguiente funcionalidad en ser habilitada en la organización.

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Nota</p></td>
<td align="left"><br><br>Los organizadores de las reuniones programadas deben tener sus buzones de correo en Exchange Online multiempresa (o en Exchange Online Dedicated vNext).</td>
</tr>
</thead>
<tbody>
</tbody>
</table>

Las siguientes opciones se pueden configurar en el nivel de inquilino para habilitar las reuniones programadas en Microsoft Teams. Estas opciones solo se aplican a usuarios profesionales y de empresa.

<table>
<thead>
<tr class="header">
<th align="left">Sección</th>
<th align="left">Configuración</th>
<th align="left">Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>Llamadas y reuniones</strong></td>
<td align="left"><p>Permitir la programación de reuniones privadas: <strong>Activado</strong></p><p>Permitir la programación de reuniones de canal: <strong>Activado</strong></p></td>
<td align="left"><p>Al habilitar esta opción, los usuarios podrán programar reuniones privadas.</p><p>Al habilitar esta opción, los usuarios podrán programar reuniones de canal.</p></td>
</tr>
</tbody>
</table>


Las reuniones programadas se pueden organizar a través del cliente de escritorio de Microsoft Teams, un navegador o Microsoft Outlook con el complemento de reuniones de Microsoft Teams. Una vez que se habilitan las reuniones programadas de Microsoft Teams, recomendamos que se comience a mostrar a los usuarios cómo se crean reuniones de Microsoft Teams o cómo se actualizan reuniones existentes de Skype Empresarial para convertirlas en reuniones de Microsoft Teams.

### <a name="rollout-of-teams-for-calling"></a>Lanzamiento de Microsoft Teams para llamadas

Las llamadas privadas es la funcionalidad de Microsoft Teams que estará en continuo desarrollo y, a lo largo del tiempo, se convertirá en un reemplazo muy atractivo de Skype Empresarial. Cuando su organización considere que las funcionalidades de llamada privada de Microsoft Teams cumplen los requisitos empresariales clave, se podrán configurar las siguientes opciones a nivel de inquilino para habilitar las llamadas privadas en Microsoft Teams. 

<table>
<thead>
<tr class="header">
<th align="left">Sección</th>
<th align="left">Configuración</th>
<th align="left">Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br>Llamadas y reuniones</strong></td>
<td align="left"><p>Permitir llamada privada: <strong>Activado</strong></p></td>
<td align="left"><p>Al habilitar esta opción, los usuarios podrán hacer llamadas privadas (audio y vídeo).</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p>Nota</p></td>
<td align="left"><br><br>Permitir que los usuarios chateen en privado: al habilitar esta opción, los usuarios podrán chatear con otros usuarios en privado.</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


En esta fase, a todos los usuarios se les debe indicar que elijan Microsoft Teams como la aplicación de llamadas preferida.

Al tener habilitadas las llamadas privadas, Microsoft Teams ofrecerá todas las funcionalidades que proporciona ahora Skype Empresarial y los usuarios podrán comenzar a usar Microsoft Teams para cumplir todos los requisitos de colaboración y comunicaciones.


<table>
<thead>
<tr class="header">
<td align="left"><p><img src="media/pilot_essentials_image2.png" /></p></td>
<td align="left">
<p><strong>Próxima acción:</strong> cuando Microsoft Teams esté funcionando en paralelo con Skype Empresarial, [genere nuevos valores a través de la adopción de usuarios](continue-journey.md), a la vez que sigue su recorrido de Skype Empresarial a Microsoft Teams.</td>
</tr>
</thead>
<tbody>
</tbody>
</table>