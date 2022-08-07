---
title: Planear la implementación para dispositivos telefónicos y pantallas de Teams
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: tony.woodruff
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
search.appverid: MET150
description: Este artículo proporciona información general sobre las tareas y los pasos para implementar los teléfonos y las pantallas de Teams en su organización.
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
ms.openlocfilehash: 5172d230823088141c58e3d2b58e1c3b579268b3
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272395"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>Planear la implementación para dispositivos telefónicos y pantallas de Teams

La implementación correcta de dispositivos telefónicos y pantallas de Teams comienza con la planificación. Este artículo le guiará por las tareas y los pasos para implementar estos dispositivos en su organización. También proporciona orientación sobre el uso de dispositivos, licencias, integración con su entorno, puntos de toque y administración.

> [!TIP]
> [El Centro de adopción de Microsoft 365](https://adoption.microsoft.com/) es un excelente lugar para empezar a trabajar en su viaje de adopción con Microsoft Teams.

## <a name="task-1-what-are-your-deployment-objectives"></a>Tarea 1: ¿Cuáles son los objetivos de implementación?

Planear la implementación de los teléfonos y las pantallas de Teams en su organización comienza con sus objetivos de implementación. Los dispositivos de Teams admiten el trabajo híbrido en salas de reuniones, oficinas y otros espacios funcionales. Tendrás que determinar dónde se usarán estos dispositivos y por quién.

### <a name="objective-identify-your-device-personas"></a>Objetivo: identificar las personas del dispositivo

Los teléfonos y pantallas de Teams se adaptarán a una de estas dos personas: 

- Dispositivos personales
- Dispositivos de espacio compartido

Los dispositivos personales y compartidos tienen diferentes roles y usos. 

**Dispositivos personales:** 

- Normalmente se asigna a un usuario, se inicia sesión con la cuenta de ese usuario y se habilita con una licencia de característica de Teams para acceder al servicio.
- Piense que los dispositivos personales tienen una relación uno a uno, con un dispositivo por usuario.
- Se puede emparejar con el cliente de escritorio de Teams y usar características como Better Together
- Puede conectarse a auriculares con micrófono, cableados o inalámbricos
- Entre las características adicionales de los dispositivos personales se incluyen escritorio rápido y pantalla de inicio. 

**Dispositivos de espacio compartido:**

- Realice una función específica, como un teléfono de área común o un dispositivo de sala de reuniones, y requiera una cuenta dedicada y una licencia de características para acceder al servicio.
- Piense que los dispositivos compartidos tienen una relación uno a varios: un dispositivo compartido por muchos usuarios.
- Se implementa en espacios compartidos, como salas de reuniones, áreas de recepción o plantas de fabricación. 
- Sus interfaces de usuario (IU) son específicas de su función, como la interfaz de usuario del teléfono de área común o la interfaz de usuario de la sala de reuniones dependen de la función y la ubicación del dispositivo compartido.
- Requiere configuración y protección opcional para asegurarse de que la configuración no cambia o para evitar que se cierre la sesión de la cuenta. 
- Entre las características adicionales de los dispositivos de espacio compartido se incluyen la búsqueda en teléfonos de área común y el hot-desking con tiempo de inactividad.

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>Objetivo: ¿Cuántos dispositivos de espacio personal y compartido necesitas?

Ahora que has identificado las personas de tu dispositivo, debes determinar qué dispositivos certificados quieres usar y cuántos de ellos necesitas. Para ayudarle a tomar esta decisión, tenga en cuenta las siguientes preguntas: 

- ¿Cuántos dispositivos personales se necesitan y quién tendrá uno?
- ¿Cuántas salas o espacios requieren dispositivos compartidos? ¿Tendrá cada espacio el mismo tipo de dispositivo? 
- ¿Tendrán que cumplir tus dispositivos los requisitos específicos?
    - Algunos ejemplos son el tamaño de pantalla, el factor de forma y el fabricante o modelo? Para obtener una lista de teléfonos y pantallas certificados, consulte [Dispositivos certificados de Microsoft Teams](teams-ip-phones.md).
-  ¿Necesita teléfonos o pantallas de Teams? Para obtener una lista de las características compatibles con los teléfonos de Teams, consulte [Teléfonos para Microsoft Teams](phones-for-teams.md#features-supported-by-teams-phones) y para obtener una lista de características compatibles con las pantallas de Teams, consulte [Pantallas de Microsoft Teams](teams-displays.md#features-supported-by-teams-displays).
- ¿Tienes dispositivos suficientes para nuevos usuarios o un proceso para nuevos pedidos y entregas?
- ¿Tendrás dispositivos de repuesto disponibles para mantenimiento o en caso de problemas de hardware? Poder intercambiar un dispositivo evita rápidamente interrupciones en la experiencia del usuario.

## <a name="task-2-what-are-your-licensing-requirements"></a>Tarea 2: ¿Cuáles son sus requisitos de licencia? 

Ahora ya sabe cuántos dispositivos necesita, el siguiente paso es determinar cuántas licencias son necesarias. Los teléfonos y las pantallas de Teams requieren licencias para acceder a Microsoft Teams y Microsoft 365.

Los dispositivos compartidos y personales necesitarán licencias diferentes. Para dispositivos personales, se pueden usar licencias asignadas a cuentas de usuario. Los dispositivos compartidos necesitan licencias específicas para su función. Para teléfonos y pantallas, las licencias aplicables son [la licencia Common Area Phone de Microsoft Teams](../set-up-common-area-phones.md#step-1---buy-the-licenses) y [la licencia de Salas de Microsoft Teams Estándar](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices).

Para obtener más información y comparar las opciones de licencia, consulte [Planes de licencias de Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1). 

## <a name="task-3-what-are-your-dependencies"></a>Tarea 3: ¿Cuáles son sus dependencias? 

### <a name="objective-plan-your-device-identities"></a>Objetivo: planear las identidades de los dispositivos

Las identidades permiten que los dispositivos tengan acceso a los servicios de Microsoft 365 y, además, deberían facilitar la detección, administración y conexión de los dispositivos dentro de su organización. Para ello, tenga en cuenta lo siguiente al planear las identidades de los dispositivos:

- Nombres principales de usuario y su formato y dominio
- Nombres para mostrar
- Detectabilidad de la libreta de direcciones
- Tipos de dispositivos de espacio personal frente a espacio compartido
- Licencias asignadas por grupo frente a usuario

### <a name="objective-review-conditional-access-policies"></a>Objetivo: Revisar las directivas de acceso condicional

Las directivas de acceso condicional de Azure Active Directory son requisitos adicionales que deben cumplirse antes de que se pueda iniciar sesión en un dispositivo.

A medida que planea la implementación

- Revise las directivas de acceso condicional existentes que puedan afectar a los teléfonos y las pantallas de Teams. Puede hacerlo en el Centro de Administración de Azure AD con la [herramienta Y si](/azure/active-directory/conditional-access/what-if-tool) y [los registros de inicio de sesión](/azure/active-directory/reports-monitoring/concept-sign-ins)

- Planear nuevas reglas si es necesario

- Use las características de acceso condicional, como los filtros de dispositivo, para aplicar reglas a los teléfonos y pantallas de Teams.

>[!NOTE]
>Hay algunas directivas de acceso condicional que los dispositivos Android no admiten. Para obtener instrucciones y procedimientos recomendados, consulte Dispositivos Android, consulte [Procedimientos recomendados de autenticación para dispositivos Android de Teams](authentication-best-practices-for-android-devices.md).

## <a name="task-4-prepare-your-environment"></a>Tarea 4: Preparar el entorno

### <a name="objective-plan-network-basics"></a>Objetivo: Planear los conceptos básicos de la red

Los dispositivos y pantallas de Teams Phone requieren acceso a Internet para conectarse a Teams y funcionar según lo previsto. Para preparar la red para su implementación, tenga en cuenta lo siguiente:

- ¿Tiene su infraestructura de red suficiente capacidad? Considere la posibilidad de los puertos del switch, los puntos de acceso inalámbrico y otra cobertura.
- Si utiliza VLA N y DHCP, ¿sus alcances tienen el tamaño en consecuencia?
- Evalúa y prueba las rutas de red desde donde se implementan los dispositivos en Microsoft 365. 
- Abra los puertos y direcciones URL de firewall necesarios para Microsoft 365 según las instrucciones.
- Revise y pruebe los requisitos y la configuración del E911 para comprobar la precisión de la ubicación y el cumplimiento. 
- Evite usar un servidor proxy y optimice las rutas de acceso a medios para obtener confiabilidad y calidad.

### <a name="objective-physical-considerations"></a>Objetivo: Consideraciones físicas

Tenga en cuenta los espacios físicos en los que se usarán los teléfonos y las pantallas de Teams.

Entre los aspectos clave se incluyen

- **Poder:** ¿Tienes suficientes tomas eléctricas? Si el dispositivo necesita una fuente de alimentación externa, ¿cómo puedes colocarlo en una toma de corriente?
- **Ubicación del dispositivo:** ¿Dónde estará físicamente tu dispositivo? Soportes de escritorio de revisión, soportes de pared y otros accesorios del fabricante de equipos originales (OEM).
- **Seguridad:** ¿Es necesario bloquear el dispositivo en determinados espacios?
- **Accesibilidad:** ¿Cumple el dispositivo los requisitos de accesibilidad de su usuario principal? Ten en cuenta dónde se coloca, la longitud del cable y la facilidad de uso del auricular o el auricular.

### <a name="task-5-how-will-you-manage-deployed-devices"></a>Tarea 5: ¿Cómo administrará los dispositivos implementados?

Los teléfonos y las pantallas de Teams se administran de dos a tres portales de Microsoft 365 y sus respectivos módulos de PowerShell: 

#### <a name="azure-active-directory-admin-center"></a>Centro de Administración de Azure Active Directory

Usar el Centro de Administración de Azure AD para administrar

- Todas las tareas relacionadas con la identidad para teléfonos y pantallas de Teams
- Directivas de acceso condicional 
- Restablecimiento de contraseña

#### <a name="teams-admin-center"></a>Centro de Administración de Teams

Usar el Centro de Administración de Teams para administrar

- [Configuración de dispositivos para Teams](../business-voice/manage-devices.md)
- [Perfiles de configuración](device-management.md#use-configuration-profiles-in-teams)
- [Etiquetado de dispositivos](manage-device-tags.md)
- [Inicio y cierre de sesión remotos](remote-sign-in-and-sign-out.md)
- Análisis de llamadas  
- Firmware
- Solución de problemas y descarga de registros

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Centro de Endpoint Manager Administración (si usas Intune para la administración de dispositivos)

Use el Centro de Endpoint Manager Administración para administrar: 

- Directivas de cumplimiento de dispositivos
- Restricciones de inscripción
- Identificadores de dispositivo corporativo
- Filtros de dispositivo
