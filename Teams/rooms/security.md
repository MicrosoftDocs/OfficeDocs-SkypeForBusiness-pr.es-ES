---
title: Seguridad de salas de Microsoft Teams
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
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo proteger los dispositivos de Salas de Microsoft Teams.
ms.openlocfilehash: d9968af4f386ed68d9a931d834082ba5362c5c33
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880894"
---
# <a name="microsoft-teams-rooms-security"></a>Seguridad de salas de Microsoft Teams

Microsoft trabaja con nuestros socios para ofrecer una solución que sea segura y no requiera acciones adicionales para proteger salas de Microsoft Teams. En este artículo se deba a muchas de las características de seguridad que se encuentran en salas de Teams.

> [!NOTE]
> Los salas de Microsoft Teams no deben tratarse como una estación de trabajo típica para el usuario final. Los casos de uso no son solo muy diferentes, sino que los perfiles de seguridad predeterminados también son muy diferentes.

Los datos limitados del usuario final se almacenan en salas de Teams. Los datos del usuario final pueden almacenarse en los archivos de registro para la solución de problemas y soporte técnico únicamente. En ningún momento, un asistente a una reunión que use salas de Teams puede copiar archivos en la unidad de disco duro o iniciar sesión como ellos mismos. No se transfieren datos del usuario final ni se puede acceder a estos mediante el dispositivo de Salas de Microsoft Teams.

Aunque los usuarios finales no pueden colocar archivos en un disco duro de Teams Rooms, Microsoft Defender sigue habilitado. El rendimiento de salas de Teams se prueba con Microsoft Defender. Deshabilitar esto o agregar software de seguridad de extremo puede producir resultados impredecibles y una posible degradación del sistema.

## <a name="hardware-security"></a>Seguridad de hardware

En un entorno de salas de Teams, hay un módulo de cálculo central que ejecuta Windows 10 IoT Enterprise Edition. Cada módulo de proceso certificado debe tener una solución de montaje seguro, una ranura de bloqueo de seguridad (por ejemplo, el bloqueo de Kensington) y medidas de seguridad de acceso de puerto de E/S para evitar la conexión de dispositivos no autorizados. También puede deshabilitar puertos específicos a través de la configuración unificada de interfaz de firmware extensible (UEFI).

Todos los módulos de proceso certificados tienen que estar habilitados de forma predeterminada con tecnología compatible con el Módulo de plataforma de confianza (TPM) 2.0. TPM se usa para cifrar la información de inicio de sesión de la cuenta de recursos de Salas de Teams.

El inicio seguro está habilitado de forma predeterminada. El arranque seguro es un estándar de seguridad desarrollado por los miembros de la industria del equipo para asegurarse de que un dispositivo es único software del fabricante de equipos originales (OEM) de confianza. Cuando se inicie el equipo, el firmware comprobará la firma de cada uno de los programas de arranque, incluidos los controladores de firmware UEFI (también conocidos como ROMs de opción), las aplicaciones EFI y el sistema operativo. Si las firmas son válidas, el equipo se autore y el firmware controla el sistema operativo. Para obtener más información, vea [Inicio seguro.](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

Solo es posible acceder a la configuración UEFI mediante la conexión de un teclado y un mouse físicos. Esto impide que pueda acceder a UEFI a través de la consola táctil de Salas de Teams, así como de cualquier otra pantalla táctil adjunta a salas de Teams.

La protección de acceso directo a la memoria (DMA) del Kernel es una configuración de Windows 10 habilitada en Salas de Teams. Con esta característica, el sistema operativo y el firmware del sistema protegen el sistema contra ataques DMA malintencionados y no deseados para todos los dispositivos compatibles con DMA:

- Durante el proceso de arranque.

- Contra DMA malintencionado por dispositivos conectados a puertos internos y externos compatibles con DMA, como las ranuras PCIe M.2 y Domain 3, durante el tiempo de ejecución del sistema operativo.

Salas de Teams también habilita la integridad de código protegida por hipervisor (HME). Una de las características proporcionadas por HNACI es la Protección de credenciales. Credential Guard proporciona las siguientes ventajas:

- **Seguridad de hardware** NTLM, Kerberos y Credential Manager aprovechan las características de seguridad de la plataforma, como el arranque seguro y la virtualización, para proteger las credenciales.

- **Seguridad basada en virtualización** Las credenciales derivadas de Windows NTLM y Kerberos, así como otros secretos, se ejecutan en un entorno protegido aislado del sistema operativo en ejecución.

- **Mayor protección frente a amenazas persistentes avanzadas** Cuando las credenciales de dominio del Administrador de credenciales, NTLM y Kerberos derivadas están protegidas con seguridad basada en virtualización, se bloquean las técnicas de ataque con robo de credenciales y las herramientas que se usan en muchos ataques dirigidos. El malware que se ejecuta en el sistema operativo con privilegios administrativos no puede extraer secretos protegidos por la seguridad basada en virtualización.

## <a name="software-security"></a>Seguridad de software

Después de la marcha de Microsoft Windows, Teams Rooms inicia sesión automáticamente en una cuenta de usuario local de Windows llamada Skype. La cuenta de Skype no tiene contraseña. Para proteger la sesión de la cuenta de Skype, se realizarán los pasos siguientes.

> [!IMPORTANT]
> No cambies la contraseña ni edites la cuenta de usuario local de Skype. Si lo hace, puede impedir que Salas de Teams inicie sesión automáticamente.

La aplicación Microsoft Teams Rooms se ejecuta con la característica Acceso asignado que se encuentra en Windows 10 1903 y versiones posteriores. Acceso asignado es una característica de Windows 10 que limita los puntos de entrada de la aplicación que se exponen al usuario. Esto es lo que habilita el modo de quiosco de una sola aplicación. Con shell Selector, Salas de Teams se configura como un dispositivo de quiosco que ejecuta una aplicación de escritorio de Windows como la interfaz de usuario. La aplicación Microsoft Teams Rooms reemplaza el shell predeterminado (explorer.exe) que se ejecuta normalmente cuando un usuario inicia sesión. En otras palabras, el shell del Explorador tradicional no se inicia en absoluto. Esto reduce en gran medida la vulnerabilidad de Microsoft Teams Rooms dentro de Windows. Para obtener más información, vea [Configurar quioscos y señales digitales en las ediciones de escritorio de Windows.](https://docs.microsoft.com/windows/configuration/kiosk-methods)

Si decide realizar un examen de seguridad o un centro de referencia de seguridad de Internet (ESA) en Salas de Teams, el examen solo puede ejecutarse en el contexto de una cuenta de administrador local, ya que la cuenta de usuario de Skype no admite la ejecución de aplicaciones que no son la aplicación Teams Rooms. Muchas de las características de seguridad aplicadas al contexto del usuario de Skype no se aplican a otros usuarios locales y, como resultado, estos exámenes de seguridad no verán el bloqueo de seguridad completo aplicado a la cuenta de Skype. Por lo tanto, no se recomienda realizar un examen local en Salas de Teams. Sin embargo, puede ejecutar pruebas de profundidad externa si así lo desea. Por este problema, le recomendamos que ejecute pruebas de contacto externo con dispositivos de Salas de Teams en lugar de realizar digitalizaciones locales.

Además, se aplican directivas de bloqueo para limitar el uso de características no administrativas. Un filtro de teclado está habilitado para interceptar y bloquear combinaciones de teclado potencialmente inseguros que no se tratan en las directivas de Acceso asignado. Solo los usuarios con derechos administrativos locales o de dominio pueden iniciar sesión en Windows para administrar salas de Teams. Estas y otras directivas aplicadas a Windows en dispositivos Microsoft Teams Rooms se evalúan y prueban continuamente durante el ciclo de vida del producto.

## <a name="account-security"></a>Seguridad de la cuenta

Los dispositivos de salas de Teams incluyen una cuenta administrativa denominada "Administrador" con una contraseña predeterminada. Le recomendamos encarecidamente que cambie la contraseña predeterminada tan pronto como sea posible después de completar la configuración.

La cuenta de administrador no es necesaria para el correcto funcionamiento de los dispositivos de Salas de Teams y se puede cambiar de nombre o incluso eliminar. Sin embargo, antes de eliminar la cuenta de administrador, asegúrese de configurar una cuenta de administrador local alternativa antes de quitar la que se incluye con los dispositivos de Teams Rooms. Para obtener más información sobre cómo cambiar la contraseña de una cuenta local de Windows mediante las herramientas integradas de Windows o PowerShell, vea lo siguiente:

- [Cambiar o restablecer la contraseña de Windows](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

También puede importar cuentas de dominio en el grupo de administradores de Windows local. Puede hacerlo para las cuentas de Azure AD mediante Intune. Para obtener más información, consulta [CSP de directiva: Grupos restringidos.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!CAUTION]
> Si elimina o deshabilita la cuenta de administrador antes de conceder permisos de administrador local a otra cuenta local o de dominio, es posible que pierda la capacidad de administrar el dispositivo de Salas de Teams. Si esto sucede, tendrá que restablecer el dispositivo a su configuración original y completar el proceso de configuración de nuevo.
>
> No conceda permisos de administrador local a la cuenta de usuario de Skype.

El Diseñador de configuración de Windows se puede usar para crear paquetes de aprovisionamiento de Windows 10. Además de cambiar la contraseña de administrador local, también puede hacer cosas como cambiar el nombre del equipo e inscribirse en Azure Active Directory. Para obtener más información sobre cómo crear un paquete de aprovisionamiento del Diseñador de configuración de Windows, consulta El aprovisionamiento de [paquetes para Windows 10.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)

Debe crear una cuenta de recurso para cada dispositivo de Salas de Teams para que pueda iniciar sesión en Teams. No puede usar la autenticación de dos factores o multifactor con esta cuenta. Exigir un segundo factor impide que la cuenta pueda iniciar sesión automáticamente en la aplicación Salas de Teams después de reiniciar. Sin embargo, puede habilitar la autenticación moderna para mayor seguridad para esta cuenta. Además, se pueden implementar directivas de acceso condicional basado en la ubicación en la cuenta del recurso para impedir el inicio de sesión en la cuenta desde una ubicación no aprobada. Para obtener más información, vea [Usar la condición de ubicación en una directiva de acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/location-condition)

Le recomendamos que cree la cuenta de recursos en Azure AD, si es posible. Aunque una cuenta sincronizada puede funcionar con Salas de Teams en implementaciones híbridas, estas cuentas sincronizadas suelen tener dificultades para iniciar sesión en Salas de Teams y pueden ser difíciles de solucionar. Si elige usar un servicio de federación de terceros para autenticar las credenciales de la cuenta de recurso, asegúrese de que el IDP de terceros responda con el `wsTrustResponse` atributo establecido en `urn:oasis:names:tc:SAML:1.0:assertion` .

## <a name="network-security"></a>Seguridad de red

Por lo general, Salas de Teams tiene los mismos requisitos de red que cualquier cliente de Microsoft Teams. El acceso a través de firewalls y otros dispositivos de seguridad es el mismo para Salas de Teams que para cualquier otro cliente de Microsoft Teams. En concreto de Salas de Teams, las categorías que se muestran como "obligatorias" para Teams deben estar abiertas en el firewall. Salas de Teams también necesita acceso a Windows Update, Microsoft Store y Microsoft Intune (si usa Microsoft Intune para administrar sus dispositivos). Para obtener la lista completa de direcciones IP y URL necesarias para salas de Microsoft Teams, vea:

- Direcciones URL e intervalos de direcciones IP de **Microsoft Teams** Office [365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Configurar WSUS de Windows Update** [](https://docs.microsoft.com/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Requisitos previos** de Microsoft Store [para Microsoft Store para Empresas y Educación](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Puntos de red** de Microsoft Intune [para Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)

Si usa el componente de servicios administrados de Salas de Microsoft Teams de Microsoft Teams Rooms Premium, también debe asegurarse de que salas de teams pueda acceder a las siguientes URL:

- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- gj3ft-hub.azure-devices.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- prod-48.westus.logic.azure.com
- prod-08.westus.logic.azure.com
- prod-62.westus.logic.azure.com
- prod-65.westus.logic.azure.com
- prod-05.westus.logic.azure.com

Salas de Teams está configurado para mantenerse revisiones automáticamente con las últimas actualizaciones de Windows, incluidas las actualizaciones de seguridad. Los salas de Teams instalan todas las actualizaciones pendientes todos los días a partir de las 14:00 con una directiva local predefinida. No es necesario usar herramientas adicionales para implementar e instalar actualizaciones de Windows. El uso de herramientas adicionales para implementar y aplicar actualizaciones puede retrasar la instalación de revisiones de Windows y, por lo tanto, llevar a una implementación menos segura. La aplicación Salas de Teams se implementa con Microsoft Store. Si sus dispositivos tienen licencia de Microsoft Teams Rooms Standard, las nuevas versiones de la aplicación se instalarán automáticamente durante el proceso de revisión nocturna. Si sus dispositivos tienen licencia con Salas de Microsoft Teams Premium e inscrito en el servicio administrado de Microsoft, se instalarán nuevas versiones de la aplicación Salas de Teams según su plan de implementación definido.

Los dispositivos De salas de Teams funcionan con la mayoría de protocolos de seguridad basados en red 802.1X u otros. Sin embargo, no podemos probar salas de Teams con todas las posibles configuraciones de seguridad de red. Por lo tanto, si surgen problemas de rendimiento que se pueden hacer seguimiento de los problemas de rendimiento de red, es posible que tenga que deshabilitar estos protocolos si están configurados en su organización.

Para obtener un rendimiento óptimo de los medios en tiempo real, le recomendamos encarecidamente que configure el tráfico multimedia de Teams para omitir servidores proxy y otros dispositivos de seguridad de red. Los medios en tiempo real son muy sensibles a la latencia y los servidores proxy, y los dispositivos de seguridad de red pueden degradar significativamente la calidad de vídeo y audio de los usuarios. Además, como los elementos multimedia de Teams ya están cifrados, ningún beneficio adicional de pasar el tráfico a través de un servidor proxy. Para obtener más información, vea Redes arriba [(en](https://docs.microsoft.com/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) la nube): un punto de vista de un arquitecto que analiza las recomendaciones de red para mejorar el rendimiento de los medios con Microsoft Teams y Salas de Microsoft Teams.

> [!IMPORTANT]
> Salas de Teams no admite servidores proxy autenticados.

Los dispositivos de Salas de Teams no necesitan conectarse a una LAN interna. Considere la posibilidad de colocar salas de Teams en un segmento de red seguro con acceso directo a Internet. Si la LAN interna está en peligro, las oportunidades de vectores de ataque hacia Salas de equipos se reducirán.

Le recomendamos encarecidamente que conecte los dispositivos de sus salas de Teams a una red cableada. El uso de redes inalámbricas en los dispositivos Teams Rooms no está recomendado ni certificado. Algunas características de conectividad, como Wi-Fi Sense, están deshabilitadas de forma predeterminada.

La unión por proximidad y otras características de salas de Teams dependen de Bluetooth. Sin embargo, Bluetooth implementación de salas de Teams no permite la conexión de un dispositivo externo a un dispositivo de Salas de Teams. Bluetooth tecnología en dispositivos Teams Rooms está limitado actualmente a la publicidad a balizas y conexiones de mensajes solicitadas. El `ADV_NONCONN_INT` tipo de unidad de datos de protocolo (PDU) se usa en la baliza de publicidad. Este tipo de PDU es para dispositivos no conectables que anuncian información al dispositivo que escucha. No es posible Bluetooth emparejamiento de dispositivos como parte de estas características. Los detalles adicionales Bluetooth sobre los protocolos se pueden encontrar en el [sitio web de Bluetooth SIG.](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)
