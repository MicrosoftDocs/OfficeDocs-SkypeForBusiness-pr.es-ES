---
title: Planificar conferencias de acceso telefónico local en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 'Resumen: Leer este tema para obtener información acerca de cómo planear para conferencias de acceso telefónico en Skype Business Server 2015.'
ms.openlocfilehash: d1e1109ff264655dc73afd26049be5844160bc0b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server-2015"></a>Planificar conferencias de acceso telefónico local en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información acerca de cómo planear para conferencias de acceso telefónico en Skype Business Server 2015.
  
Conferencia de marcado es una característica opcional de Skype para Business Server que permite a los asistentes de la reunión para unirse a la parte de audio de una reunión mediante una llamada la reunión desde un teléfono. La conferencia de acceso telefónico local es un subconjunto de la conferencia de audio y requiere configuración adicional. En este tema se describe lo que necesita considerar antes de la implementación de la conferencia de acceso telefónico local en la organización. 
  
Algunos de los componentes necesarios para las conferencias de marcado son específicas a las conferencias de acceso telefónico y algunos son componentes de Telefonía IP empresarial. Aunque la conferencia de acceso telefónico local usa algunos de los mismos componentes que usa la telefonía IP empresarial, puede implementar la conferencia de acceso telefónico local aunque no implemente la telefonía IP empresarial. En esta sección se describen los componentes que se necesitan para las conferencias de acceso telefónico local. Para obtener más información acerca de cómo planear una solución de Telefonía IP empresarial completa, vea [Planear la solución de Telefonía IP empresarial en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).
  
La conferencia de acceso telefónico local requiere que proporcione conectividad a la red telefónica conmutada (RTC) al implementar un servidor de mediación. Además de implementar un servidor de mediación, necesita tener en cuenta los siguientes puntos para permitir la conferencia de acceso telefónico local en la organización:
  
- El plan para conectarse a la red telefónica conmutada (RTC)
    
- El plan para los planes de marcado, números de acceso y las regiones de conferencia
    
- El plan para crear directorios de conferencia
    
- La directiva de conferencias para permitir acceso telefónico
    
- Asistencia para usuarios de empresa y anónimos
    
> [!NOTE]
> Si implementa conferencias de acceso telefónico, debe implementarlo en cada grupo donde implementar Skype para conferencias de Business Server. No es necesario que asigne números de acceso (los números a los que llaman los participantes para unirse a una conferencia) en cada uno de los grupos de servidores, pero necesitará implementar la característica de acceso telefónico local en todos ellos. Este requisito admite la característica de nombre grabado cuando un usuario llama a un número de acceso de un grupo para unirse a un Skype para conferencia Business Server en un grupo diferente. 
  
## <a name="plan-for-pstn-connectivity"></a>Planificar la conectividad con RTC

La conferencia de acceso telefónico requiere al menos un servidor de mediación y al menos una puerta de enlace de telefónica pública conmutada (PSTN) de la red. 
  
Puede implementar un servidor de mediación en un sitio central o en un sitio de sucursal. En un sitio central, puede instalar un servidor de mediación en un grupo de servidores front-end o en un servidor Standard Edition, o bien puede implementarlo en un servidor o en un grupo de servidores independiente. En un sitio de sucursal, puede implementar un servidor de mediación en un servidor independiente o como componente de la aplicación de sucursal con funciones de supervivencia.
  
Puede implementar una puerta de enlace RTC en un sitio central o en un sitio de sucursal. En un sitio de sucursal, la puerta de enlace RTC puede ser independiente o un componente de la aplicación de sucursal con funciones de supervivencia.
  
Para obtener más información acerca de servidor de mediación y requisitos de puerta de enlace PSTN, vea [componentes de servidor de mediación en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md), [implementar un servidor de mediación en el generador de topología en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)y [definir una puerta de enlace en El generador de topología en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/define-a-gateway.md).
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a>Plan para los planes de marcado, números de acceso y las regiones de conferencia

Para configurar la conferencia de acceso telefónico local, crea planes de marcado y números de acceso a conferencias de acceso telefónico local. También especifica las regiones de acceso telefónico local que asocian un número de acceso a conferencias de acceso telefónico local con sus planes de marcado. Más concretamente:
  
- Los planes de marcado son conjuntos de reglas de normalización que especifican el número y el patrón de dígitos de un número de teléfono y convierten el número de teléfono al formato E.164 estándar obligatorio para el enrutamiento de llamadas.
    
- Los números de acceso a conferencias de acceso telefónico local son números a los que pueden llamar los usuarios para participar en una conferencia.
    
- Cada número de acceso a conferencias de acceso telefónico local necesita estar asociado por lo menos con un plan de marcado. 
    
- Cada plan de marcado está asociado con una región de conferencia.
    
Al crear un plan de marcado, especifica la región de conferencia de acceso telefónico local que se aplica al plan de marcado. Cuando crea el número de acceso telefónico local, selecciona las regiones que asocian el número de acceso con los planes de marcado pertinentes.
  
También especifica el ámbito del mismo: ámbito de usuario, ámbito de grupo de servidores o ámbito de sitio. A cada usuario se le asigna el plan de marcado correspondiente al ámbito más limitado que se aplica al usuario. Por ejemplo, se asigna a un usuario un plan de marcado de nivel de usuario, si procede. Si no tiene aplicado ningún plan de marcado de nivel de usuario, se le asignará un plan de marcado de nivel de grupo de servidores. Si no tiene aplicado ningún plan de marcado de nivel de grupo de servidores, se le asignará un plan de marcado de nivel de sitio. Si no tiene aplicado ningún plan de marcado de nivel de sitio, se le asignará el plan de marcado global. 
  
Antes de configurar los planes de marcado, es importante planear qué nombres desea aplicar a las regiones y cómo desea usarlas. Las consideraciones siguientes necesitan aplicarse a las regiones de conferencia de acceso telefónico local:
  
- Una región es, por lo general, un área geográfica asociada con una oficina o con un grupo de oficinas.
    
- Los números de acceso telefónico local están asociados a idiomas. Si admite áreas geográficas con varios idiomas, tendrá que decidir cómo desea definir las regiones para que admitan los diferentes idiomas. Por ejemplo, puede definir varias regiones según una combinación de zona geográfica e idioma, o bien puede definir una única región según la zona geográfica y tener números de acceso telefónico local distintos para cada idioma.
    
- Cuando un usuario programa una reunión, de forma predeterminada la reunión usa la región especificada por el plan de marcado del usuario.
    
- De forma predeterminada, todos los números de acceso telefónico local de la región se incluyen en la invitación a la reunión.
    
- Es importante asignar un nombre a las regiones de modo que puedan reconocerse claramente. El usuario puede usar los nombres de las regiones para cambiar una región de una reunión de modo que los distintos números de acceso se incluyan en la invitación. (Cuando los usuarios utilizan Outlook para programar una reunión, el usuario utiliza el complemento de reunión en línea de Skype para empresas para cambiar la región).
    
- Las regiones necesitan asignarse de tal modo que cualquier invitado que quiera obtener acceso a una conferencia pueda ver un número de acceso local en la invitación a la misma.
    
- Puede configurar el orden de acceso aparecen números dentro de una región en la página de configuración conferencias de acceso telefónico (y, por tanto, el orden en que aparecen en la invitación a la conferencia) mediante Skype para los cmdlets del Shell de administración de servidor de Business.
    
- Cualquier usuario puede llamar al número de acceso telefónico local que desee para unirse a una conferencia desde cualquier ubicación.
    
Para obtener más información acerca de cómo crear un plan de marcado, consulte [crear o modificar un plan de marcado de Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md) y [crear o modificar una regla de normalización de Skype para el año 2015 Business](../../deploy/deploy-enterprise-voice/normalization-rules.md). 
  
## <a name="plan-for-conference-directories"></a>Planificar directorios de conferencia

Directorios de conferencia mantienen una asignación entre el ID alfanumérico que un participante se utiliza para unirse a una conferencia al utilizar Skype para el negocio y el ID de conferencia sólo numérico que un participante de la conferencia de acceso telefónico utiliza para unirse a la conferencia. El formato del identificador de conferencia es el siguiente:
  
```
<housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>
```

Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias. En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo de servidores. Si aplica esta sugerencia, los Id. de conferencia, por lo general, se mantendrán cortos. Ahora bien, una vez que entre los diferentes grupos de servidores haya más de 9 directorios de conferencia, el número de Id. de conferencia crecerá para facilitar la creación de nuevas conferencias.
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a>Planificar una directiva de conferencia que permite acceso telefónico local

Conferencias deben habilitarse para acceso telefónico cuando se configuran las directivas de la conferencia. De forma predeterminada, las conferencias habilitadas para el acceso telefónico local incluyen la siguiente información en la invitación a la conferencia:
  
- Un identificador de conferencia numérico que identifica la conferencia
    
- Uno o más números de acceso de RTC
    
- Un vínculo a una página de Configuración de conferencias de acceso telefónico local, que contiene una lista completa de números de acceso con sus idiomas asociados; un lugar para crear, restablecer o desbloquear números de identificación personal (PIN); y otra información, como, por ejemplo, los controles de tono de marcado de frecuencia múltiple (DTMF)
    
Para obtener más información acerca de las directivas de la conferencia, consulte [Configurar acceso telefónico conferencia en Skype para Business Server 2015](../../deploy/deploy-conferencing/dial-in-conferencing.md) y [Administrar directivas de conferencia en Skype para Business Server 2015](../../manage/conferencing/conferencing-policies.md).  

## <a name="support-for-enterprise-and-anonymous-users"></a>Asistencia para usuarios de empresa y anónimos

Las conferencias de acceso telefónico local admiten tanto a usuarios de empresa como a usuarios anónimos. Los usuarios de Enterprise tienen credenciales de servicios de dominio de Active Directory y Skype para cuentas Business Server dentro de su organización. Los usuarios anónimos no tienen credenciales de empresa en la organización. En el contexto de la conferencia de acceso telefónico, un usuario de la organización de un socio federado que utiliza la red PSTN para conectarse a una conferencia se trata como un usuario anónimo. A diferencia de lo que ocurre en otros contextos, los usuarios federados no se autentican para la conferencia de acceso telefónico local.
  
Los usuarios de empresa o coordinadores de la conferencia que se unen a una conferencia habilitada para el acceso telefónico local, marcan uno de los números de acceso a la conferencia y, luego, se les pide que escriban el identificador de la conferencia. Si todavía no se ha unido a la reunión ningún coordinador, los usuarios pueden escribir su extensión (o número de teléfono completo) de comunicaciones unificadas (UC) y el PIN, o bien esperar a que un coordinador les admita. El organizador de la reunión puede unirse a la reunión como coordinador escribiendo solo el PIN. El servidor front-end usa la combinación de la extensión o número de teléfono completo y el PIN para asignar únicamente usuarios de empresa a sus credenciales de Active Directory. Como resultado, los usuarios de empresa se pueden autenticar e identificar por su nombre en la conferencia. Los usuarios de empresa también pueden asumir un rol de conferencia definido previamente por el organizador.
  
> [!NOTE]
> Los usuarios empresariales que llamen desde un teléfono IP de office o desde Skype para operador de servidor empresarial no le pedirá su número de teléfono porque ya se autentican. 
  
Los usuarios anónimos que deseen unirse a una conferencia de acceso telefónico local, necesitan marcar uno de los números de acceso a la conferencia y, luego, se les pedirá que escriban el identificador de la conferencia. A los usuarios anónimos sin autenticar también se les pide que registren su nombre. El nombre grabado identifica a los usuarios sin autenticar en la conferencia. No se admiten usuarios anónimos en la conferencia hasta que se haya unido a ella al menos un coordinador o un usuario autenticado, y no se les puede asignar un rol definido previamente.
  
> [!NOTE]
> Los usuarios de empresa que elijan no escribir su número de teléfono y su PIN no se autenticarán. Se les pedirá que registren su nombre y se les considerará usuarios anónimos en la conferencia. 
  
Al programar una reunión, el organizador de la reunión puede restringir el acceso a la reunión cerrándola o bloqueándola. En este caso, se solicitará a los usuarios de acceso telefónico local que se autentiquen. 
  
- Si los usuarios de acceso telefónico prefieren no autenticarse o no lo hacen correctamente, se les transferirá a la sala de espera, donde esperarán hasta que el coordinador acepte o rechace su entrada, o bien hasta que se agote el tiempo de espera y sean desconectados.
    
- Una vez admitidos en una conferencia, los usuarios de acceso telefónico local pueden participar en la parte de audio de la conferencia y usar los comandos de tono de marcado de frecuencia múltiple (DTMF) por medio de las teclas del teléfono.
    
- Los coordinadores de acceso telefónico pueden usar comandos DTMF para activar o desactivar el audio de los participantes, bloquear o desbloquear la conferencia, admitir a personas de la sala de espera y activar o desactivar los anuncios de entrada y salida.
    
- Los coordinadores también pueden usar un comando DTMF para admitir a todas las personas de la sala de espera, lo que modifica los permisos de la reunión para habilitar a todos los que se unan más tarde. 
    
- Todos los participantes de acceso telefónico pueden usar comandos DTMF para escuchar la Ayuda, escuchar la lista de conferencias y silenciarse.
    
- Los participantes de acceso telefónico (es decir, los participantes que accedan o no desde el RTC) oirán anuncios personales durante la conferencia, como si han sido silenciados o se les ha dado la voz, si la reunión está siendo grabada o si hay alguien esperando en la sala de espera.
    
    > [!NOTE]
    > Los participantes que se unan a la conferencia haciendo clic en un vínculo, en lugar de acceder por medio del marcado telefónico, no oirán anuncios personales. 
  

