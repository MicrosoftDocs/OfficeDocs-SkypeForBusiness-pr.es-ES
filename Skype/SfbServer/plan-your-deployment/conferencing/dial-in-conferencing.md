---
title: Plan for dial-in conferencing in Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 'Resumen: lea este tema para obtener información sobre la planeación de conferencias de acceso telefónico local en Skype Empresarial Server.'
ms.openlocfilehash: 963f8dd29cce1e086fd797b2872000ab5cb7b1c80e7c9884675f8a89c43cbebc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349982"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a>Plan for dial-in conferencing in Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre la planeación de conferencias de acceso telefónico local en Skype Empresarial Server.
  
La conferencia de acceso telefónico local es una característica opcional de Skype Empresarial Server que permite a los asistentes a la reunión unirse a la parte de audio de una reunión llamando a la reunión desde un teléfono. La conferencia de acceso telefónico local es un subconjunto de la conferencia de audio y requiere configuración adicional. En este tema se describe lo que debe pensar antes de implementar conferencias de acceso telefónico local para su organización. 
  
Algunos de los componentes necesarios para las conferencias de acceso telefónico local son específicos de las conferencias de acceso telefónico local y otros son Telefonía IP empresarial de acceso telefónico local. Aunque las conferencias de acceso telefónico local usan algunos de los mismos componentes que Telefonía IP empresarial, puede implementar conferencias de acceso telefónico local incluso si no implementa Telefonía IP empresarial. En esta sección se describen los componentes necesarios para las conferencias de acceso telefónico local. Para obtener más información acerca de cómo planear una solución Telefonía IP empresarial completa, vea [Plan your Telefonía IP empresarial solution in Skype Empresarial Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).
  
Las conferencias de acceso telefónico local requieren que proporcione conectividad a la red telefónica conmutada (RTC) mediante la implementación de un servidor de mediación. Además de implementar un servidor de mediación, debe tener en cuenta lo siguiente para permitir conferencias de acceso telefónico local para su organización:
  
- Su plan para conectarse a la red telefónica conmutada (RTC)
    
- Su plan para planes de marcado, números de acceso y regiones de conferencia
    
- Su plan para crear directorios de conferencia
    
- Su directiva de conferencia para permitir el acceso telefónico local
    
- Compatibilidad con usuarios anónimos y empresariales
    
> [!NOTE]
> Si implementa conferencias de acceso telefónico local, debe implementarla en todos los servidores en los que implemente Skype Empresarial Server conferencia. No es necesario asignar números de acceso (los números que los participantes llaman para unirse a una conferencia) en todos los grupos, pero debe implementar la característica de acceso telefónico en cada grupo. Este requisito admite la característica de nombre grabado cuando un usuario llama a un número de acceso de un grupo para unirse a una Skype Empresarial Server conferencia en un grupo diferente. 
  
## <a name="plan-for-pstn-connectivity"></a>Planeación de la conectividad RTC

Las conferencias de acceso telefónico local requieren al menos un servidor de mediación y al menos una puerta de enlace de red telefónica conmutada (RTC). 
  
Puede implementar un servidor de mediación en un sitio central o en un sitio de sucursal. En un sitio central, puede colocar un servidor de mediación en un grupo de servidores front-end o un servidor Standard Edition, o bien puede implementarlo en un servidor o grupo independiente. En un sitio de sucursal, puede implementar un servidor de mediación en un servidor independiente o como un componente de la aplicación de sucursal con funciones de supervivencia.
  
Puede implementar una puerta de enlace RTC en un sitio central o en un sitio de sucursal. En un sitio de sucursal, la puerta de enlace RTC puede ser independiente o un componente de la aplicación de sucursal con funciones de supervivencia.
  
Para obtener más información sobre los requisitos del servidor de mediación y la puerta de enlace RTC, vea Mediation [Server component in Skype Empresarial Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md), Deploy a Mediation Server in [Topology Builder in Skype Empresarial Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)y Define a gateway in [Topology Builder in Skype Empresarial Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a>Planear planes de marcado, números de acceso y regiones de conferencia

Para configurar las conferencias de acceso telefónico local, cree planes de marcado y números de acceso de conferencia de acceso telefónico local. También se especifican las regiones de acceso telefónico local que asocian un número de acceso de conferencia de acceso telefónico local con sus planes de marcado. Más concretamente:
  
- Los planes de marcado son conjuntos de reglas de normalización que especifican el número y el patrón de dígitos de un número de teléfono y traducen el número de teléfono al formato E.164 estándar necesario para el enrutamiento de llamadas.
    
- Los números de acceso a conferencias de acceso telefónico local son números a los que pueden llamar los usuarios para participar en una conferencia.
    
- Cada número de acceso a conferencias de acceso telefónico local debe estar asociado por lo menos con un plan de marcado. 
    
- Cada plan de marcado está asociado a una región de conferencia.
    
Al crear un plan de marcado, se especifica la región de conferencia de acceso telefónico local que se aplica al plan de marcado. Cuando se crea el número de acceso telefónico local, se seleccionan las regiones que asocian el número de acceso con los planes de marcado pertinentes.
  
También se especifica el ámbito del plan de marcado: ámbito de usuario, ámbito de grupo o ámbito de sitio. A cada usuario se asigna el plan de marcado correspondiente al ámbito más limitado que se aplica al usuario. Por ejemplo, se asigna a un usuario un plan de marcado de nivel de usuario, si procede. Si no tiene aplicado ningún plan de marcado de nivel de usuario, se le asignará un plan de marcado de nivel de grupo de servidores. Si no tiene aplicado ningún plan de marcado de nivel de grupo de servidores, se le asignará un plan de marcado de nivel de sitio. Si no tiene aplicado ningún plan de marcado de nivel de sitio, se le asignará el plan de marcado global. 
  
Antes de configurar los planes de marcado, es importante planear qué nombres desea aplicar a las regiones y cómo desea usarlas. Las consideraciones siguientes deben aplicarse a las regiones de conferencia de acceso telefónico local:
  
- Una región es, por lo general, un área geográfica asociada con una oficina o con un grupo de oficinas.
    
- Los números de acceso telefónico local están asociados a idiomas. Si admite áreas geográficas con varios idiomas, tendrá que decidir cómo desea definir las regiones para que admitan los diferentes idiomas. Por ejemplo, puede definir varias regiones según una combinación de zona geográfica e idioma, o bien puede definir una única región según la zona geográfica y tener números de acceso telefónico local distintos para cada idioma.
    
- Cuando un usuario programa una reunión, de forma predeterminada la reunión usa la región especificada por el plan de marcado del usuario.
    
- De forma predeterminada, todos los números de acceso telefónico para la región se incluyen en la invitación a la reunión.
    
- Es importante asignar un nombre a las regiones de modo que puedan reconocerse claramente. El usuario puede usar los nombres de las regiones para cambiar una región de una reunión de modo que los distintos números de acceso se incluyan en la invitación. (Cuando los usuarios usan Outlook para programar una reunión, el usuario usa el complemento de reunión en línea para Skype Empresarial para cambiar la región).
    
- Las regiones deben asignarse de tal modo que cualquier invitado que quiera obtener acceso a una conferencia pueda ver un número de acceso local en la invitación a la misma.
    
- Puede configurar el orden en que aparecen los números de acceso dentro de una región en la página Configuración conferencia de acceso telefónico local (y, por lo tanto, el orden en que aparecen en la invitación de conferencia) mediante cmdlets del Shell de administración de Skype Empresarial Server.
    
- Cualquier usuario puede llamar al número de acceso telefónico local que desee para unirse a una conferencia desde cualquier ubicación.
    
Para obtener más información acerca de la creación de un plan de marcado, vea [Create or modify a dial plan in Skype Empresarial Server](../../deploy/deploy-enterprise-voice/dial-plans.md) y Create or modify a [normalization rule in Skype Empresarial](../../deploy/deploy-enterprise-voice/normalization-rules.md). 
  
## <a name="plan-for-conference-directories"></a>Planeación de directorios de conferencia

Los directorios de conferencia mantienen una asignación entre el identificador de reunión alfanumérico que un participante usa para unirse a una conferencia al usar Skype Empresarial y el identificador de conferencia de solo numérico que usa un participante de conferencia de acceso telefónico local para unirse a la conferencia. El formato del identificador de conferencia es el siguiente:
  

\<housekeeping digit (1 digit)\>\<conference directory (usually 1-2 digits)\>\<conference number (variable number of digits\>\<check digit (1 digit)\>


Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias. En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo de servidores. Con esta directriz, los IDs de conferencia generalmente se pueden mantener pequeños. Ahora bien, una vez que entre los diferentes grupos de servidores haya más de 9 directorios de conferencia, el número de Id. de conferencia crecerá para facilitar la creación de nuevas conferencias.
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a>Planear una directiva de conferencia que permita el acceso telefónico local

Las conferencias deben estar habilitadas para el acceso telefónico local al configurar directivas de conferencia. De forma predeterminada, las conferencias habilitadas para el acceso telefónico local incluyen la siguiente información en la invitación a la conferencia:
  
- Id. de conferencia numérico que identifica la conferencia
    
- Uno o más números de acceso RTC
    
- Un vínculo a una página de conferencia de acceso telefónico Configuración, que contiene una lista completa de números de acceso con sus idiomas asociados; un lugar para crear, restablecer o desbloquear números de identificación personal (PIN); y otra información, como los controles de frecuencia múltiple de tono dual (DTMF)
    
Para obtener más información acerca de las directivas de conferencia, vea [Configure dial-in conferencing in Skype Empresarial Server](../../deploy/deploy-conferencing/dial-in-conferencing.md) and Manage [conferencing policies in Skype Empresarial Server](../../manage/conferencing/conferencing-policies.md).  

## <a name="support-for-enterprise-and-anonymous-users"></a>Compatibilidad con usuarios anónimos y empresariales

Las conferencias de acceso telefónico local admiten tanto a usuarios de empresa como a usuarios anónimos. Enterprise usuarios tienen credenciales de Servicios de dominio de Active Directory y Skype Empresarial Server cuentas dentro de su organización. Los usuarios anónimos no tienen credenciales de empresa en la organización. En el contexto de conferencia de acceso telefónico local, un usuario de la organización de un asociado federado que usa la RTC para conectarse a una conferencia se trata como un usuario anónimo. A diferencia de lo que ocurre en otros contextos, los usuarios federados no se autentican para la conferencia de acceso telefónico local.
  
Los usuarios de empresa o coordinadores de la conferencia que se unen a una conferencia habilitada para el acceso telefónico local marcan uno de los números de acceso a la conferencia y, a continuación, se les pide que escriban el identificador de la conferencia. Si todavía no se ha unido a la reunión ningún coordinador, los usuarios pueden escribir su extensión (o número de teléfono completo) de comunicaciones unificadas (UC) y el PIN, o bien esperar a que un coordinador les admita. El organizador de la reunión puede unirse a la reunión como coordinador escribiendo solo el PIN. El servidor front-end usa la combinación de número de teléfono completo o extensión, y PIN, para asignar de forma única a los usuarios empresariales sus credenciales de Active Directory. Como resultado, los usuarios de empresa se pueden autenticar e identificar por su nombre en la conferencia. Los usuarios de empresa también pueden asumir un rol de conferencia definido previamente por el organizador.
  
> [!NOTE]
> Enterprise usuarios que llamen desde un teléfono IP de oficina o desde Skype Empresarial Server Attendant no se les pedirá su número de teléfono porque ya están autenticados. 
  
Los usuarios anónimos que deseen unirse a una conferencia de acceso telefónico local, deben marcar uno de los números de acceso a la conferencia y, a continuación, se les pedirá que escriban el identificador de la conferencia. A los usuarios anónimos sin autenticar también se les pide que registren su nombre. El nombre grabado identifica a los usuarios sin autenticar en la conferencia. No se admiten usuarios anónimos en la conferencia hasta que se haya unido a ella al menos un coordinador o un usuario autenticado, y no se les puede asignar un rol definido previamente.
  
> [!NOTE]
> Los usuarios de empresa que elijan no escribir su número de teléfono y su PIN no se autenticarán. Se les pedirá que registren su nombre y se les considerará usuarios anónimos en la conferencia. 
  
Al programar una reunión, el organizador de la reunión puede elegir restringir el acceso a la reunión mediante el cierre o bloqueo de la reunión. En este caso, se solicita a los usuarios de acceso telefónico que se autentiquen. 
  
- Si los usuarios de acceso telefónico local fallan o deciden no autenticarse, se transfieren a la sala de espera donde se transfieren hasta que un líder los acepta o los rechaza, o se les pasa el tiempo de espera y se desconectan.
    
- Una vez admitidos en una conferencia, los usuarios de acceso telefónico telefónico pueden participar en la parte de audio de la conferencia y pueden ejercer comandos de tono dual multifrecuencia (DTMF) mediante el teclado del teléfono.
    
- Los líderes de acceso telefónico pueden ejercer comandos DTMF para activar o desactivar la capacidad de los participantes para activar o desactivar la mancha, bloquear o desbloquear la conferencia, admitir personas de la sala de espera y activar o desactivar los anuncios de entrada y salida.
    
- Los líderes también pueden usar un comando DTMF para admitir a todos los usuarios de la sala de espera, lo que cambia los permisos de la reunión para permitir a cualquier persona que se una posteriormente. 
    
- Todos los participantes de acceso telefónico pueden ejercer comandos DTMF para escuchar ayuda, escuchar la lista de conferencias y silenciarse.
    
- Los participantes de acceso telefónico local (es decir, si marcan o no desde la RTC) escuchan anuncios personales durante la conferencia, como si se han silenciado o no, si la reunión se está grabando o si alguien está esperando en la sala de espera.
    
    > [!NOTE]
    > Los participantes que se unan a la conferencia haciendo clic en un vínculo, en lugar de acceder mediante el marcado telefónico, no oirán anuncios personales. 
  

