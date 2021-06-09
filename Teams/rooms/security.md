---
title: Salas de Microsoft Teams Seguridad
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
description: Obtenga información sobre cómo proteger sus Salas de Microsoft Teams dispositivos.
ms.openlocfilehash: 24faadb4e139bdbddd8ed315faba7fd8c8257b83
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796704"
---
# <a name="microsoft-teams-rooms-security"></a>Salas de Microsoft Teams Seguridad

Microsoft trabaja con nuestros partners para ofrecer una solución segura y no requiere acciones adicionales para proteger Salas de Microsoft Teams. En este artículo se debatió sobre muchas de las características de seguridad que se encuentran en Salas de Teams.

> [!NOTE]
> Salas de Microsoft Teams debe tratarse como una estación de trabajo de usuario final típica. Los casos de uso no solo son muy diferentes, sino que los perfiles de seguridad predeterminados también son muy diferentes.
> Este artículo se aplica a Salas de Microsoft Teams dispositivos que se ejecutan en Windows.

Los datos limitados del usuario final se almacenan en Salas de Teams. Es posible que los datos del usuario final se almacenen en los archivos de registro para la solución de problemas y solo soporte técnico. En ningún momento puede un asistente de una reunión Salas de Teams copiar archivos en el disco duro o iniciar sesión como ellos mismos. No se transfiere ningún dato del usuario final al dispositivo Salas de Microsoft Teams accesible.

Aunque los usuarios finales no pueden colocar archivos en Salas de Teams disco duro, Microsoft Defender sigue habilitado. Salas de Teams rendimiento se prueba con Microsoft Defender. Deshabilitar esto o agregar software de seguridad de punto de conexión puede provocar resultados impredecibles y una posible degradación del sistema.

## <a name="hardware-security"></a>Seguridad de hardware

En un Salas de Teams, hay un módulo de proceso central que se ejecuta Windows 10 IoT Enterprise edición. Cada módulo de proceso certificado debe tener una solución de montaje seguro, una ranura de bloqueo de seguridad (por ejemplo, bloqueo de Kensington) y medidas de seguridad de acceso al puerto de E/S para evitar la conexión de dispositivos no autorizados. También puede deshabilitar puertos específicos mediante la configuración de interfaz de firmware extensible unificada (UEFI).

Todos los módulos de proceso certificados deben enviarse con tecnología compatible con el Módulo de plataforma de confianza (TPM) 2.0 habilitada de forma predeterminada. TPM se usa para cifrar la información de inicio de sesión de Salas de Teams cuenta de recursos.

El inicio seguro está habilitado de forma predeterminada. El inicio seguro es un estándar de seguridad desarrollado por los miembros del sector de pc para ayudar a asegurarse de que un dispositivo se inicia usando solo software de confianza del Fabricante de equipos originales (OEM). Cuando se inicia el equipo, el firmware comprueba la firma de cada parte del software de inicio, incluidos los controladores de firmware UEFI (también conocidos como ROM de opción), las aplicaciones EFI y el sistema operativo. Si las firmas son válidas, el equipo inicia y el firmware da control al sistema operativo. Para obtener más información, vea [Inicio seguro.](/windows-hardware/design/device-experiences/oem-secure-boot)

Solo es posible acceder a la configuración de UEFI adjuntando un teclado físico y un mouse. Esto impide que pueda obtener acceso Salas de Teams UEFI a través de la consola táctil, así como de cualquier otra pantalla táctil conectada a Salas de Teams.

La protección de acceso directo a memoria (DMA) del kernel es una Windows 10 que está habilitada en Salas de Teams. Con esta característica, el sistema operativo y el firmware del sistema protegen el sistema contra ataques DMA malintencionados y no intencionados para todos los dispositivos compatibles con DMA:

- Durante el proceso de inicio.

- Contra DMA malintencionado por dispositivos conectados a puertos compatibles con DMA internos y externos fácilmente accesibles, como las ranuras PCIe M.2 y Thunderbolt 3, durante el tiempo de ejecución del sistema operativo.

Salas de Teams también habilita la integridad del código protegido por hipervisor (HVCI). Una de las características proporcionadas por HVCI es Credential Guard. Protección de credenciales proporciona las siguientes ventajas:

- **Seguridad de hardware** NTLM, Kerberos y Credential Manager aprovechan las características de seguridad de la plataforma, como el inicio seguro y la virtualización, para proteger las credenciales.

- **Las credenciales de** seguridad basadas en Windows NTLM y Kerberos y otros secretos se ejecutan en un entorno protegido aislado del sistema operativo en ejecución.

- **Mejor protección contra amenazas persistentes avanzadas** Cuando las credenciales de dominio de Credential Manager, NTLM y Kerberos se protegen con seguridad basada en virtualización, las técnicas y herramientas de ataque de robo de credenciales que se usan en muchos ataques dirigidos se bloquean. El malware que se ejecuta en el sistema operativo con privilegios administrativos no puede extraer secretos protegidos por la seguridad basada en virtualización.

## <a name="software-security"></a>Seguridad de software

Después de iniciar Windows Microsoft, Salas de Teams inicia sesión automáticamente en una cuenta de usuario Windows local denominada Skype. La Skype cuenta no tiene contraseña. Para que la sesión Skype cuenta sea segura, se realizarán los pasos siguientes.

> [!IMPORTANT]
> No cambie la contraseña ni edite la cuenta de Skype usuario local. Si lo hace, Salas de Teams iniciar sesión automáticamente.

La Salas de Microsoft Teams se ejecuta con la característica Acceso asignado que se encuentra en Windows 10 1903 y versiones posteriores. Acceso asignado es una característica de Windows 10 que limita los puntos de entrada de la aplicación expuestos al usuario. Esto es lo que permite el modo de quiosco de una sola aplicación. Con shell Selector, Salas de Teams se configura como un dispositivo de quiosco que ejecuta una Windows de escritorio como la interfaz de usuario. La Salas de Microsoft Teams aplicación reemplaza el shell predeterminado (explorer.exe) que normalmente se ejecuta cuando un usuario inicia sesión. En otras palabras, el shell tradicional del Explorador no se inicia en absoluto. Esto reduce en gran medida la Salas de Microsoft Teams de vulnerabilidad dentro de Windows. Para obtener más información, vea [Configurar quioscos y señales digitales en Windows ediciones de escritorio.](/windows/configuration/kiosk-methods)

Si decide ejecutar un examen de seguridad o un punto de referencia del Centro de seguridad de Internet (CIS) en Salas de Teams, el examen solo puede ejecutarse en el contexto de una cuenta de administrador local, ya que la cuenta de usuario de Skype no admite la ejecución de aplicaciones que no son la aplicación Salas de Teams. Muchas de las características de seguridad aplicadas al contexto de usuario de Skype no se aplican a otros usuarios locales y, como resultado, estos análisis de seguridad no verán el bloqueo de seguridad completo aplicado Skype la cuenta. Por lo tanto, no se recomienda ejecutar un examen local en Salas de Teams. Sin embargo, puede ejecutar pruebas de penetración externa si así lo desea. Debido a esto, le recomendamos que ejecute pruebas de penetración externa en Salas de Teams dispositivos en lugar de ejecutar exploraciones locales.

Además, se aplican directivas de bloqueo para limitar el uso de características no administrativas. Un filtro de teclado está habilitado para interceptar y bloquear combinaciones de teclado potencialmente inseguras que no están cubiertas por directivas de Acceso asignado. Solo los usuarios con derechos administrativos locales o de dominio pueden iniciar sesión Windows administrar Salas de Teams. Estas y otras directivas aplicadas a Windows dispositivos Salas de Microsoft Teams se evalúan y prueban continuamente durante el ciclo de vida del producto.

## <a name="account-security"></a>Seguridad de la cuenta

Salas de Teams dispositivos incluyen una cuenta administrativa denominada "Administrador" con una contraseña predeterminada. Le recomendamos encarecidamente que cambie la contraseña predeterminada tan pronto como sea posible después de completar la configuración.

La cuenta de administrador no es necesaria para el correcto funcionamiento de Salas de Teams dispositivos y se puede cambiar el nombre o incluso eliminarse. Sin embargo, antes de eliminar la cuenta de administrador, asegúrese de configurar una cuenta de administrador local alternativa configurada antes de quitar la que se incluye con Salas de Teams dispositivos. Para obtener más información sobre cómo cambiar una contraseña para una cuenta de Windows local con herramientas Windows integradas o PowerShell, vea lo siguiente:

- [Cambiar o restablecer la contraseña Windows contraseña](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

También puede importar cuentas de dominio en el grupo Windows administrador local. Puede hacerlo para cuentas de Azure AD mediante Intune. Para obtener más información, vea [CSP de directiva: grupos restringidos.](/windows/client-management/mdm/policy-csp-restrictedgroups).

> [!CAUTION]
> Si elimina o deshabilita la cuenta de administrador antes de conceder permisos de administrador local a otra cuenta local o de dominio, es posible que pierda la capacidad de administrar el Salas de Teams dispositivo. Si esto sucede, tendrás que restablecer el dispositivo de nuevo a la configuración original y completar el proceso de configuración de nuevo.
>
> No conceda permisos de administrador local a la cuenta Skype usuario.

Windows El Diseñador de configuración se puede usar para crear Windows 10 paquetes de aprovisionamiento. Además de cambiar la contraseña de administrador local, también puede hacer cosas como cambiar el nombre del equipo e inscribirse en Azure Active Directory. Para obtener más información sobre cómo crear un Windows de aprovisionamiento del Diseñador de configuración, vea [Aprovisionar paquetes para Windows 10](/windows/configuration/provisioning-packages/provisioning-packages).

Debe crear una cuenta de recursos para cada Salas de Teams dispositivo para que pueda iniciar sesión en Teams. No puede usar la autenticación de dos factores o multifactor con esta cuenta. Requerir un segundo factor impediría que la cuenta pueda iniciar sesión automáticamente en la aplicación Salas de Teams después de un reinicio. Sin embargo, puede habilitar la autenticación moderna para obtener seguridad adicional para esta cuenta. Además, se pueden implementar directivas de acceso condicional basadas en ubicación para la cuenta de recursos para evitar que inicie sesión en la cuenta desde una ubicación no aprobada. Para obtener más información, vea [Usar la condición de ubicación en una directiva de acceso condicional](/azure/active-directory/conditional-access/location-condition)

Le recomendamos que cree la cuenta de recursos en Azure AD, si es posible. Aunque una cuenta sincronizada puede funcionar con Salas de Teams en implementaciones híbridas, estas cuentas sincronizadas a menudo tienen dificultades para iniciar sesión en Salas de Teams y pueden ser difíciles de solucionar. Si elige usar un servicio de federación de terceros para autenticar las credenciales de la cuenta de recursos, asegúrese de que el IDP de terceros responde con el `wsTrustResponse` atributo establecido en `urn:oasis:names:tc:SAML:1.0:assertion` .

## <a name="network-security"></a>Seguridad de red

Por lo general, Salas de Teams los mismos requisitos de red que cualquier Microsoft Teams cliente. El acceso a través de firewalls y otros dispositivos de seguridad es el mismo para Salas de Teams que para cualquier otro Microsoft Teams cliente. Específicas de Salas de Teams, las categorías que aparecen como "necesarias" para Teams deben estar abiertas en el firewall. Salas de Teams también necesita acceso a Windows, Microsoft Store y Microsoft Intune (si usa Microsoft Intune para administrar sus dispositivos). Para obtener la lista completa de direcciones IP y direcciones URL necesarias para Salas de Microsoft Teams, vea:

- **Microsoft Teams** [Office 365 direcciones URL e intervalos de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows configurar** [WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft Store** [requisitos previos para Microsoft Store para Empresas educación](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [network enpoints para Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Si usa el componente Salas de Microsoft Teams de servicios administrados de Salas de Microsoft Teams Premium, también debe asegurarse de que Salas de Teams acceso a las siguientes direcciones URL:

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

Salas de Teams está configurado para mantenerse automáticamente parcheado con las últimas Windows actualizaciones, incluidas las actualizaciones de seguridad. Salas de Teams instala todas las actualizaciones pendientes todos los días a partir de las 2:00 a.m. con una directiva local predefinida. No es necesario usar herramientas adicionales para implementar y aplicar Windows actualizaciones. Usar herramientas adicionales para implementar y aplicar actualizaciones puede retrasar la instalación de Windows revisiones y, por lo tanto, llevar a una implementación menos segura. La Salas de Teams aplicación se implementa con el Microsoft Store. Si los dispositivos tienen licencia con Salas de Microsoft Teams Estándar, las nuevas versiones de la aplicación se instalan automáticamente durante el proceso de revisión nocturna. Si los dispositivos tienen licencia Salas de Microsoft Teams Premium y están inscritos en el Servicio administrado de Microsoft, se instalarán nuevas versiones de la aplicación Salas de Teams según su plan de implementación definido.

Salas de Teams dispositivos funcionan con la mayoría de los protocolos de seguridad 802.1X u otros protocolos de seguridad basados en red. Sin embargo, no podemos probar Salas de Teams con todas las configuraciones de seguridad de red posibles. Por lo tanto, si surgen problemas de rendimiento que se pueden rastrear a problemas de rendimiento de red, es posible que tenga que deshabilitar estos protocolos si están configurados en su organización.

Para un rendimiento óptimo de los medios en tiempo real, le recomendamos encarecidamente que configure el tráfico Teams multimedia para omitir los servidores proxy y otros dispositivos de seguridad de red. Los medios en tiempo real son muy sensibles a la latencia y los servidores proxy y los dispositivos de seguridad de red pueden degradar significativamente la calidad de audio y vídeo de los usuarios. Además, como Teams multimedia ya está cifrado, no hay ningún beneficio concreto al pasar el tráfico a través de un servidor proxy. Para obtener más información, vea Conexión de red (a la [nube):](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) un punto de vista de un arquitecto que analiza las recomendaciones de red para mejorar el rendimiento de los medios con Microsoft Teams y Salas de Microsoft Teams.

> [!IMPORTANT]
> Salas de Teams no admite servidores proxy autenticados.

Salas de Teams dispositivos no necesitan conectarse a una LAN interna. Considere la posibilidad de Salas de Teams en un segmento de red seguro con acceso directo a Internet. Si la LAN interna se ve comprometida, las oportunidades de vectores de ataque hacia Salas de Teams se reducirán.

Le recomendamos encarecidamente que conecte sus dispositivos Salas de Teams a una red cableada. El uso de redes inalámbricas en Salas de Teams dispositivos no está recomendado ni certificado. Algunas características de conectividad, como Wi-Fi Sense, están deshabilitadas de forma predeterminada.

La combinación de proximidad y otras Salas de Teams características dependen de Bluetooth. Sin embargo, Bluetooth implementación en Salas de Teams dispositivos no permite una conexión de dispositivo externo a un Salas de Teams dispositivo. Bluetooth uso de tecnología en Salas de Teams dispositivos está limitado actualmente a balizas de publicidad y conexiones próximas. El `ADV_NONCONN_INT` tipo de unidad de datos de protocolo (PDU) se usa en la baliza de publicidad. Este tipo de PDU es para dispositivos no conectables que anuncian información al dispositivo de escucha. No hay ningún Bluetooth de dispositivo como parte de estas características. Puede encontrar más detalles Bluetooth protocolos en el sitio web Bluetooth [SIG.](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)
