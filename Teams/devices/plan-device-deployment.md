---
title: Planear la implementación para dispositivos Teams teléfono y Pantallas
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
description: Este artículo proporciona información general sobre las tareas y los pasos para implementar Teams teléfonos y pantallas en su organización.
ms.openlocfilehash: 2ad9840d6ebd1ac6973027dedf6be294704f5326
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2021
ms.locfileid: "61577804"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>Planear la implementación para dispositivos Teams teléfono y Pantallas

Una implementación correcta de Teams teléfonos y Teams pantallas comienza con la planificación. Este artículo le llevará a través de las tareas y los pasos para implementar estos dispositivos en su organización. También proporciona instrucciones sobre el uso de dispositivos, las licencias, la integración con su entorno, los puntos de contacto y la administración.

> [!TIP]
> [El Microsoft 365 de](https://adoption.microsoft.com/) adopción es un excelente lugar para empezar a realizar el viaje de adopción con Microsoft Teams.

## <a name="task-1-what-are-your-deployment-objectives"></a>Tarea 1: ¿Cuáles son sus objetivos de implementación?

La planificación de la implementación de Teams teléfonos y pantallas de su organización comienza con los objetivos de implementación. Teams dispositivos admiten el trabajo híbrido en salas de reuniones, oficinas y otros espacios funcionales. Tendrás que determinar dónde se usarán estos dispositivos y quién.

### <a name="objective-identify-your-device-personas"></a>Objetivo: Identificar las personas del dispositivo

Teams teléfonos y pantallas se ajustarán a una de las dos personas: 

- Dispositivos personales
- Dispositivos de espacio compartido

Los dispositivos personales y compartidos tienen diferentes roles y usos. 

**Dispositivos personales:** 

- Normalmente se asigna a un usuario, se ha iniciado sesión con la cuenta de ese usuario y se habilita con una Teams de características para acceder al servicio.
- Piense que los dispositivos personales tienen una relación uno a uno, con un dispositivo por usuario.
- Se puede emparejar con el Teams de escritorio y usar características como Better Together
- Puede conectarse a auriculares, cableados o inalámbricos
- Entre las características adicionales de los dispositivos personales se incluyen el escritorio en caliente y la pantalla de inicio. 

**Dispositivos de espacio compartido:**

- Realice una función específica, como un teléfono de área común o un dispositivo de la sala de reuniones y requiera una cuenta y una licencia de características dedicadas para acceder al servicio.
- Piense que los dispositivos compartidos tienen una relación uno a varios: un dispositivo compartido por muchos usuarios.
- Se implementa en espacios compartidos como salas de reuniones, áreas de recepción o pisos de fabricación. 
- Sus interfaces de usuario (IU) son específicas de su función, como área común Teléfono interfaz de usuario o la interfaz de usuario de la sala de reuniones dependen de la función y la ubicación del dispositivo compartido.
- Requiera la configuración y el endurecimiento opcional para asegurarse de que la configuración no cambia o para evitar que la cuenta se desescriba. 
- Entre las características adicionales de los dispositivos de espacio compartido se incluyen la búsqueda en teléfonos de área común y el escritorio en caliente con tiempo de espera inactivo

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>Objetivo: ¿Cuántos dispositivos de espacio personal y compartido necesita?

Ahora que ha identificado las personas del dispositivo, debe determinar qué dispositivos certificados desea usar y cuántos de ellos necesita. Para ayudarle a tomar esta decisión, tenga en cuenta las siguientes preguntas: 

- ¿Cuántos dispositivos personales son necesarios y quién tendrá uno?
- ¿Cuántos espacios o salas requieren dispositivos compartidos? ¿Cada espacio tendrá el mismo tipo de dispositivo? 
- ¿Necesitarán sus dispositivos cumplir requisitos específicos?
    - Algunos ejemplos son el tamaño de pantalla, el factor de forma y el fabricante o modelo. Para obtener una lista de teléfonos y pantallas certificados, [vea Microsoft Teams dispositivos certificados.](teams-ip-phones.md)
-  ¿Necesita Teams teléfonos o Teams pantallas? Para obtener una lista de características compatibles con Teams teléfonos, vea Teléfonos para [Microsoft Teams](phones-for-teams.md#features-supported-by-teams-phones) y para obtener una lista de características compatibles con Teams pantallas, vea [Microsoft Teams pantallas.](teams-displays.md#features-supported-by-teams-displays)
- ¿Tiene suficientes dispositivos para nuevos usuarios o un proceso para nuevos pedidos y entregas?
- ¿Tendrá dispositivos de repuesto disponibles para mantenimiento o en caso de problemas de hardware? Poder intercambiar un dispositivo rápidamente evita interrupciones en la experiencia del usuario.

## <a name="task-2-what-are-your-licensing-requirements"></a>Tarea 2: ¿Cuáles son sus requisitos de licencia? 

Ahora ya sabe cuántos dispositivos necesita, el siguiente paso es determinar cuántas licencias son necesarias. Teams teléfonos y pantallas requieren licencias para acceder a Microsoft Teams y Microsoft 365.

Los dispositivos compartidos y personales necesitarán licencias diferentes. Para dispositivos personales, se pueden usar licencias asignadas a cuentas de usuario. Los dispositivos compartidos necesitan licencias específicas de su función. Para teléfonos y pantallas, las licencias aplicables son el área común [Teléfono](../set-up-common-area-phones.md#step-1---buy-the-licenses) licencia para Microsoft Teams y la [Salas de Microsoft Teams Estándar licencia.](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices)

Para obtener más información y comparar las opciones de licencia, [vea Microsoft 365 planes de licencias.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 

## <a name="task-3-what-are-your-dependencies"></a>Tarea 3: ¿Cuáles son sus dependencias? 

### <a name="objective-plan-your-device-identities"></a>Objetivo: Planear las identidades de dispositivo

Las identidades permiten que los dispositivos accedan Microsoft 365 servicios y deben facilitar la descubriendo, administrando y conectando dispositivos dentro de su organización. Para ello, tenga en cuenta lo siguiente al planear las identidades de dispositivo:

- Nombres principales de usuario y su formato y dominio
- Mostrar nombres
- Detectabilidad de libreta de direcciones
- Tipos de dispositivos de espacio personal frente a compartidos
- Agrupar frente a licencias asignadas por el usuario

### <a name="objective-review-conditional-access-policies"></a>Objetivo: Revisar directivas de acceso condicional

Azure Active Directory directivas de acceso condicional son requisitos adicionales que deben cumplirse antes de que un dispositivo pueda haber iniciado sesión.

A medida que planee la implementación

- Revise las directivas de acceso condicional existentes que podrían afectar a Teams teléfonos y pantallas. Puede hacerlo en el Centro de administración de Azure AD con la herramienta [¿Qué sucede?](/azure/active-directory/conditional-access/what-if-tool) y los registros [de inicio de sesión](/azure/active-directory/reports-monitoring/concept-sign-ins)

- Planear nuevas reglas si es necesario

- Use características de acceso condicional como filtros de dispositivo para aplicar reglas a Teams teléfonos y pantallas.

>[!NOTE]
>Hay algunas directivas de acceso condicional que los dispositivos Android no admiten. Para obtener instrucciones y procedimientos recomendados, vea Dispositivos Android, vea Procedimientos recomendados de autenticación [para Teams dispositivos Android.](authentication-best-practices-for-android-devices.md)

## <a name="task-4-prepare-your-environment"></a>Tarea 4: Preparar el entorno

### <a name="objective-plan-network-basics"></a>Objetivo: Planear conceptos básicos de red

Teams Teléfono dispositivos y pantallas requieren acceso a Internet para conectarse a Teams y funcionar según lo previsto. Para preparar la red para la implementación, tenga en cuenta lo siguiente:

- ¿La infraestructura de red tiene suficiente capacidad? Considere cambiar de puerto, puntos de acceso inalámbricos y otra cobertura.
- Si usa VLAN y DHCP, ¿tienen el tamaño de los ámbitos en consecuencia?
- Evalúe y pruebe las rutas de red desde donde se implementan los dispositivos Microsoft 365. 
- Abra los puertos y direcciones URL del firewall necesarios Microsoft 365 según las instrucciones.
- Revise y pruebe los requisitos y la configuración de E911 para obtener precisión y cumplimiento de la ubicación. 
- Evite usar un servidor proxy y optimice las rutas multimedia para obtener confiabilidad y calidad.

### <a name="objective-physical-considerations"></a>Objetivo: Consideraciones físicas

Tenga en cuenta los espacios físicos en los que se Teams teléfonos y pantallas se usarán.

Entre los aspectos clave se incluyen

- **Potencia:** ¿Tiene suficientes tomas de corriente eléctrica? Si el dispositivo necesita una fuente de alimentación externa, ¿qué tan cerca se puede colocar en una toma de corriente?
- **Ubicación del dispositivo:** ¿Dónde estará físicamente el dispositivo? Soportes de escritorio de revisión, soportes de pared y otros accesorios del fabricante de equipos original (OEM).
- **Seguridad:** ¿Es necesario bloquear el dispositivo en determinados espacios?
- **Accesibilidad:** ¿Cumple el dispositivo los requisitos de accesibilidad de su usuario principal? Tenga en cuenta dónde se coloca, la longitud del cable y la facilidad de uso de auriculares o auriculares.

### <a name="task-5-how-will-you-manage-deployed-devices"></a>Tarea 5: ¿Cómo administrará los dispositivos implementados?

Teams teléfonos y pantallas se administran de dos a tres portales de Microsoft 365 y sus respectivos módulos de PowerShell: 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory de administración

Usar el centro Azure AD administración para administrar

- Todas las tareas relacionadas con la identidad Teams teléfonos y pantallas
- Directivas de acceso condicional 
- Restablecimientos de contraseña

#### <a name="teams-admin-center"></a>Teams de administración

Usar el Centro Teams administración para administrar

- [Configuración del dispositivo para Teams](../business-voice/manage-devices.md)
- [Perfiles de configuración](device-management.md#use-configuration-profiles-in-teams)
- [Etiquetado de dispositivos](manage-device-tags.md)
- [Inicio de sesión y salida remotos](remote-sign-in-and-sign-out.md)
- Análisis de llamadas  
- Firmware
- Solución de problemas y descarga de registros

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Endpoint Manager de administración (si usa Intune para la administración de dispositivos)

Use el centro Endpoint Manager administración para administrar: 

- Directivas de cumplimiento de dispositivos
- Restricciones de inscripción
- Identificadores de dispositivos corporativos
- Filtros de dispositivo
