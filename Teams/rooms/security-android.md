---
title: Seguridad de Microsoft Teams para Android
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Obtenga información sobre cómo proteger Microsoft Teams para dispositivos Android.
ms.openlocfilehash: 6d17cc68af8ef4a879d5de3b17d27f20b281ddf8
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532440"
---
# <a name="microsoft-teams-for-android-security"></a>Seguridad de Microsoft Teams para Android

Este artículo no cubre los dispositivos Android configurados para el modo de dispositivo dedicado por Microsoft Endpoint Manager. Los dispositivos Android de Teams se ejecutan en modo de pantalla completa por diseño. Para obtener información sobre el quiosco de Android, consulta [Inscripción de dispositivos dedicados de Android Enterprise](/mem/intune/enrollment/android-kiosk-enroll).

Microsoft trabaja con nuestros asociados OEM para ofrecer una solución que sea segura por diseño y personalizable para satisfacer las necesidades de los clientes. En este artículo se describen muchas de las características de seguridad que se encuentran en los dispositivos Android de Teams y nuestro enfoque. Se divide en cuatro secciones clave para facilitar la navegación.

> [!NOTE]
> Los dispositivos Android de Microsoft Teams no deben tratarse como un dispositivo Android típico. Los dispositivos Android de Teams son dispositivos específicos diseñados para usarse con Teams y sus respectivos casos de uso. Este artículo se aplica solo a los dispositivos microsoft teams certificados y dedicados que ejecutan el sistema operativo Android. Los dispositivos certificados de Teams solo se pueden comprar a proveedores OEM certificados. Para obtener información sobre los dispositivos Android certificados por Microsoft Teams, consulte [Dispositivos Android certificados para Microsoft Teams](/microsoftteams/devices/teams-ip-phones).

Para obtener información sobre la seguridad de Salas de Teams para dispositivos Windows, consulta [Salas de Microsoft Teams de seguridad de Windows](security-windows.md).

## <a name="software-security"></a>Seguridad del software

### <a name="android-kiosk-mode"></a>Modo de pantalla completa de Android

Los dispositivos Android de Teams están bloqueados para ejecutar solo las aplicaciones aprobadas ejecutando el dispositivo en modo de pantalla completa de Android. El modo de pantalla completa deshabilita el acceso a cualquier capacidad del iniciador y ayuda a proteger el dispositivo, de modo que las aplicaciones autorizadas se inicien en el dispositivo.  

| Nombre de la aplicación            | Descripción de la aplicación                   |
|-----------------------------|-------------------------------------------|
| Aplicación De Microsoft Teams para Android | Aplicación de dispositivos de Microsoft Teams        |
| Agente de Administración de Microsoft Teams | Administración remota del Centro de administración de Teams      |
| Portal de empresa de Intune       | Inscripción del dispositivo, registro & inicio de sesión |
| Agente de partners OEM           | Agente de partners OEM & aplicación Configuración de dispositivos   |

Por motivos de diseño, la aplicación Microsoft Teams para Android se iniciará en el modo de pantalla completa de Android y no proporciona al usuario acceso al sistema operativo ni acceso a componentes fuera de la experiencia de usuario designada de Teams.

### <a name="application-code-signing"></a>Firma de código de aplicación

Todas las aplicaciones De Microsoft y OEM tienen un código firmado. La firma de código ayuda a validar que el software que se ejecuta en un dispositivo es original de Microsoft y de nuestros asociados de hardware. La firma de código también intenta validar la integridad del software que se ejecuta en el dispositivo, de modo que solo se pueda iniciar y ejecutar software original.  

### <a name="third-party-applications"></a>Aplicaciones de terceros

Los dispositivos certificados por Teams no tienen google play store, Amazon App Store o Google Play Services instalados por diseño. Esto ayuda a garantizar que no se puedan instalar aplicaciones de terceros desde store en un dispositivo.  

### <a name="android-debug-bridge"></a>Puente de depuración de Android

El puente de depuración de Android (ADB) está deshabilitado por diseño en todos los dispositivos Android de Teams que ejecuten software de versión. ADB es una herramienta de línea de comandos que permite a los administradores realizar funciones en dispositivos basados en Android y permite la instalación de aplicaciones, el acceso al shell de dispositivos y otras funciones de administración.  

### <a name="file-system-encryption"></a>Cifrado del sistema de archivos

Los dispositivos Android de Teams deben admitir el cifrado basado en Android y se pueden aplicar mediante las directivas de cumplimiento de Microsoft Endpoint Manager. Para obtener información sobre las directivas de cumplimiento de [Endpoint Manager Use Endpoint Manager directivas de cumplimiento para establecer reglas para los dispositivos que administra con Intune](/mem/intune/protect/device-compliance-get-started).

### <a name="android-os-version"></a>Versión del sistema operativo Android

Los dispositivos Android de Teams ejecutan versiones compatibles de Android. El sistema operativo Android lo administran los partners OEM, se combinan con el firmware certificado de Teams y, a continuación, se envía a los dispositivos desde el Centro de administración de Teams. Para obtener información sobre qué versiones de Android se ejecutan en dispositivos Android de Teams, consulte [Dispositivos Android certificados por Microsoft Teams](/microsoftteams/devices/teams-ip-phones).

### <a name="android-security-updates"></a>Actualizaciones de seguridad de Android

Los proveedores OEM, como parte del proceso de actualización de firmware, incorporan las líneas base de actualización de seguridad de Android adecuadas para ayudar a garantizar la seguridad del sistema operativo base. Mantener los dispositivos actualizados periódicamente es importante para asegurarse de que se ejecutan las actualizaciones de seguridad adecuadas de Android en sus dispositivos. Para obtener más información, consulta al fabricante del dispositivo.

### <a name="account-security"></a>Seguridad de la cuenta

Los dispositivos Android de Teams se crean en torno a dos tipos de cuentas que permiten el funcionamiento correcto de un dispositivo.

- Cuenta de administrador de dispositivos locales

- Cuenta de usuario o recurso  

Los dispositivos Android de Teams también son compatibles con algunas directivas de acceso condicional, que se pueden usar como capas de seguridad adicionales para el inicio de sesión en dispositivos. Para conocer los procedimientos recomendados y las directivas de acceso condicional admitidas, vea [Directivas de cumplimiento de acceso condicional compatibles](/microsoftteams/rooms/supported-ca-and-compliance-policies).

### <a name="local-device-administrator-account"></a>Cuenta de administrador de dispositivos locales

Los dispositivos Android de Teams incluyen una cuenta administrativa para acceder a la configuración del dispositivo, el servidor web local si está instalado y cualquier configuración específica del OEM.

Los elementos iniciales de configuración y configuración del dispositivo, como el nombre de usuario y la contraseña predeterminados para esta cuenta, se pueden obtener del fabricante del dispositivo.

> [!CAUTION]
> Asegúrate de cambiar la contraseña de administrador de dispositivos local tan pronto como sea posible.  

> [!TIP]
> El Centro de administración de Teams se puede usar para cambiar la contraseña de administrador de dispositivos locales de un dispositivo Android con sesión iniciada en Teams aplicando un perfil de configuración. Recomendamos este enfoque después de iniciar sesión en el dispositivo inicial para proteger las características elevadas de un dispositivo Android. Las características elevadas pueden incluir la configuración del dispositivo y los portales de administración web, si son compatibles.

### <a name="user-or-resource-account"></a>Cuenta de usuario o recurso

Los dispositivos Android de Teams requieren el uso de una cuenta de usuario o de recursos dedicados para iniciar sesión en Microsoft 365. Intentamos proteger estas cuentas de maneras específicas, dependiendo de si se trata de una cuenta de usuario normal para un dispositivo personal o una cuenta de recurso para un dispositivo compartido. Para obtener más información, vea [Crear y configurar cuentas de recursos para salas y dispositivos compartidos](/microsoftteams/rooms/with-office-365).

### <a name="device-updates"></a>Actualizaciones de dispositivos

Los dispositivos Android de Teams están configurados para descargar actualizaciones certificadas por Microsoft desde el Centro de administración de Teams cuando estén disponibles. Un administrador puede invocarlas de forma automática o manual. Las herramientas de terceros de nuestros asociados OEM también están disponibles para realizar esta función si es necesario. Los dispositivos Android de Teams pueden instalar actualizaciones fuera del horario laboral para evitar que afecten a los usuarios. Las programaciones fuera del horario laboral se pueden configurar en el Centro de administración de Teams o mediante herramientas de terceros de partners OEM.

> [!IMPORTANT]
> Microsoft recomienda que la administración del firmware para todos los dispositivos Android de Teams se haga a través del Centro de administración de Teams.

## <a name="network-security"></a>Seguridad de red

Los dispositivos Android de Teams tienen los mismos requisitos de red que cualquier cliente de Microsoft Teams, incluido el acceso a través de firewalls y otros dispositivos de seguridad. En concreto, las categorías enumeradas como **necesarias** para Teams deben estar abiertas en el firewall junto con otros servicios auxiliares, como se indica a continuación. Para obtener la lista completa de direcciones IP y URL necesarias para dispositivos Android de Teams, consulte:

- Microsoft Teams, Exchange Online, SharePoint Online, Común de Microsoft 365 y Office Online [Office 365 DIRECCIONES URL e intervalo de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges)

- [Microsoft Intune puntos de conexión de red para Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Los dispositivos Android de Teams funcionan con la mayoría de los protocolos de seguridad 802.1X y otros basados en red. Sin embargo, no podemos probar los dispositivos Android de Teams con todas las configuraciones de seguridad de red. Por lo tanto, si surgen problemas de rendimiento que pueden rastrearse hasta problemas de rendimiento de la red, es posible que debas deshabilitar estos protocolos si están configurados en tu organización o ponerte en contacto con el partner OEM para obtener ayuda.

Para obtener un rendimiento óptimo de los medios en tiempo real, le recomendamos que configure el tráfico multimedia de Teams para omitir los servidores proxy y otros dispositivos de seguridad de red. Los medios en tiempo real son sensibles a la latencia de red, que pueden deberse a servidores proxy y otros dispositivos de seguridad de red. La latencia de red puede degradar significativamente la calidad de audio y vídeo de los usuarios. Para obtener más información, consulte [Redes (en la nube): punto de vista de un arquitecto](/microsoft-365/solutions/networking-design-principles) que analiza las recomendaciones de red para mejorar el rendimiento de los medios con Microsoft Teams.

Los dispositivos Android de Teams usan comunicaciones cifradas y autenticación de extremo en Internet. Los dispositivos Android de Teams usan TLS 1.2 y posterior.  

> [!IMPORTANT]
> Los dispositivos Android de Teams no admiten los servidores proxy autenticados ni las restricciones de inquilino. Ponte en contacto con tu partner OEM para obtener información de soporte técnico de proxy.

Los dispositivos Android de Teams no necesitan conectarse a una LAN interna. Considere la posibilidad de colocar dispositivos Android de Teams en un segmento de red segura con acceso directo a Internet. Por ejemplo, los teléfonos de Teams se podrían implementar en una VLAN de voz. Si su LAN interna se ve comprometida, las oportunidades de vectores de ataque hacia los dispositivos Android de Teams se reducirán mediante la implementación de esta segregación de red.

Le recomendamos encarecidamente que conecte sus dispositivos Android de Teams a una red cableada. El uso de redes inalámbricas requiere una cuidadosa planificación y evaluación para obtener la mejor experiencia.

Los paneles Proximity Join, Better Together, Teams Cast y el emparejamiento de paneles de Teams dependen de Bluetooth. El uso de tecnología Bluetooth en Salas de Teams para dispositivos Android está limitado actualmente a balizas publicitarias y conexiones próximas. El `ADV_NONCONN_INT` tipo de unidad de datos de protocolo (PDU) se usa en la baliza de publicidad. Este tipo de PDU es para dispositivos no conectables que anuncian información al dispositivo de escucha. No hay emparejamiento de dispositivos Bluetooth como parte de estas características. Puedes encontrar más detalles sobre los protocolos Bluetooth en el sitio web de Bluetooth SIG.

Los teléfonos y pantallas de Teams ofrecen la funcionalidad de emparejamiento bluetooth para emparejarse con auriculares con el perfil de Hands-Free Bluetooth.

Para obtener más información sobre la seguridad en Microsoft Teams, consulte [Seguridad y Microsoft Teams](/microsoftteams/teams-security-guide).  
