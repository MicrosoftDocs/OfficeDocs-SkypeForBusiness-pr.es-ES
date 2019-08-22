---
title: Configurar un controlador de borde de sesión para varios inquilinos
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Aprenda a configurar un controlador de borde de sesión (SBC) para que sirva a varios inquilinos.
ms.openlocfilehash: a8ee395a0b588af976151923992efbb32971b43c
ms.sourcegitcommit: f2cdb2c1abc2c347d4dbdca659e026a08e60ac11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "36493131"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurar un controlador de borde de sesión para varios inquilinos

El enrutamiento directo admite la configuración de un controlador de borde de sesión (SBC) para que sirva a varios inquilinos.

> [!NOTE]
> Este escenario está diseñado para socios de Microsoft y/o para operadores de RTC, denominados operadores de telefonía más adelante en este documento. Un transportista vende servicios de telefonía que se envían a Microsoft Teams a sus clientes. 

Un transportista:
- Implementa y administra un SBC en su centro de proceso de información (los clientes no necesitan implementar un SBC y reciben servicios de telefonía del transportista en el cliente de Teams).
- Conecta la SBC a varios inquilinos.
- Proporciona servicios RTC a los clientes.
- Administra la calidad de las llamadas de un extremo a otro.
- Cargos por separado para los servicios RTC.

Microsoft no administra transportistas. Microsoft ofrece un sistema PBX (Microsoft Phone System) y un cliente de equipo, certifica teléfonos y certifica SBCs, que puede usarse con el sistema telefónico de Microsoft. Antes de elegir un operador, asegúrese de que su elección tiene un SBC certificado y puede administrar la calidad de voz de un extremo a otro.

Estos son los pasos técnicos de implementación para configurar el escenario.

**Solo para operadores:**
1. Implemente la SBC y configúrela para el escenario de hospedaje según las [instrucciones de los proveedores de SBC certificados](#deploy-and-configure-the-sbc).
2. Registre un nombre de dominio base en el inquilino del operador y solicite un certificado comodín.
3. Registrar un subdominio para cada cliente, que es parte del dominio base.

**Transportista con un administrador global del cliente:**
1. Agregue el nombre de subdominio al inquilino del cliente.
2. Activar el nombre del subdominio.
3. Configure el tronco desde el transportista hasta el espacio empresarial del cliente y aprovisione usuarios.

*Asegúrese de comprender los conceptos básicos de DNS y de cómo se administra el nombre de dominio en Office 365. Revise [obtener ayuda con los dominios de Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) antes de continuar.*

## <a name="deploy-and-configure-the-sbc"></a>Implementar y configurar la SBC

Para conocer los pasos detallados sobre cómo implementar y configurar SBCs para un escenario de hospedaje de SBC, consulte la documentación del proveedor de SBC.

- **AudioCodes:** [Notas de configuración de enrutamiento directo](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), la configuración del escenario de hospedaje de SBC, descrito en "conexión de SBC AudioCodes a Microsoft Teams Direct Routing modelo Hosting Model." 
- **Oracle:** Las [notas de configuración de enrutamiento directo](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html), la configuración del escenario de hospedaje de SBC se describe en la sección "Microsoft". 
- **Comunicaciones de la cinta de opciones:**  Consulte la guía de [configuración básica de Microsoft Teams](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) en la cinta de opciones de SBC de comunicaciones para obtener información sobre cómo configurar la serie de núcleos de la cinta SBCS y a esta página [mejor práctica de la cinta: configuración de operadores para Microsoft Teams enrutamiento directo de SBC Borde](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)
- **Te-Systems (anynode):**  Regístrese en la página de la [comunidad de los sistemas](https://community.te-systems.de/) para obtener documentación y ejemplos sobre cómo configurar SBC de anynode para varios inquilinos.

> [!NOTE]
> Preste atención a cómo configurar el encabezado "contacto". El encabezado de contacto se usa para buscar el inquilino del cliente en el mensaje entrante. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrar un dominio base y subdominios

Para el escenario de hospedaje, necesita crear:
- Un nombre de dominio base de la propiedad del transportista.
- Subdominio que forma parte del nombre de dominio base de todos los inquilinos de cliente.

En el siguiente ejemplo:
- Adatum es un portador que sirve a varios clientes proporcionando servicios de telefonía y de Internet.
- Woodgrove Bank, contoso y Adventure Works son tres clientes que tienen los dominios de Office 365, pero reciben los servicios de telefonía de Adatum.

Los subdominios **deben** coincidir con el nombre de FQDN del tronco que se configurará para el cliente y el FQDN en el encabezado del contacto al enviar la invitación a Office 365. 

Cuando una llamada llega a la interfaz de enrutamiento directo de Office 365, la interfaz usa el encabezado del contacto para buscar el inquilino donde se debe buscar el usuario. El enrutamiento directo no usa la búsqueda de números de teléfono en la invitación, ya que es posible que algunos clientes tengan números no realizados que pueden superponerse en varios inquilinos. Por lo tanto, el nombre de dominio completo en el encabezado del contacto es necesario para identificar el inquilino exacto para buscar al usuario por el número de teléfono.

*Consulte [obtener ayuda con los dominios de office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obtener más información sobre cómo crear nombres de dominio en inquilinos de Office 365.*

En el diagrama siguiente se resumen los requisitos para el dominio, los subdominios y el encabezado de contacto básicos.

![Diagrama que muestra los requisitos para los dominios y el encabezado del contacto](media/direct-routing-1-sbc-requirements.png)

La SBC necesita un certificado para autenticar las conexiones. Para el escenario de hospedaje de SBC, el proveedor debe solicitar un certificado con San * \*. base_domain (por ejemplo \*, customers.adatum.BIZ)*. Este certificado se puede usar para autenticar conexiones a varios inquilinos servidos desde un único SBC.

La siguiente tabla es un ejemplo de una configuración.


|Nuevo nombre de dominio |Tipo|Registra  |SAN de certificado para SBC  |Dominio predeterminado del inquilino en el ejemplo  |Nombre FQDN que SBC debe presentar en el encabezado del contacto al enviar llamadas a los usuarios|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Básica     |     En el inquilino del operador  |    \*. customers.adatum.biz  |   adatum.biz      |NA, este es un inquilino de servicio, sin usuarios |
|sbc1.customers.adatum.biz|    Subdominio  |    En un espacio empresarial de cliente  |    \*. customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Subdominio | En un espacio empresarial de cliente   |   \*. customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Subdominio | En un espacio empresarial de cliente |   \*. customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

Para configurar la base y los subdominios, siga los pasos que se describen a continuación. En el ejemplo, configuraremos un nombre de dominio base (customers.adatum.biz) y un subdominio para un cliente (sbc1.customers.adatum.biz en inquilino de Woodgrove Bank).

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrar un nombre de dominio base en el inquilino de la portadora

**Estas acciones se realizan en el inquilino del transportista.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Asegurarse de que tiene los derechos adecuados en el inquilino del transportista

Solo puede agregar dominios nuevos si inició sesión en el centro de administración de Microsoft 365 como administrador global. 

Para validar el rol que tiene, inicie sesión en el centro de administración de Microsoft 365https://portal.office.com)(, vaya **** > a usuarios**activos**y, a continuación, compruebe que tiene un rol de administrador global. 

Para obtener más información acerca de los roles de administrador y cómo asignar un rol en Office 365, consulte [acerca de los roles de administrador de office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Agregar un dominio base al inquilino y comprobarlo

1.  En el centro de administración de Microsoft 365, vaya a**dominios** > de **configuración** > **Agregar dominio**.
2.  En el cuadro **Escriba un dominio** , escriba el FQDN del dominio base. En el ejemplo siguiente, el dominio base es *customers.adatum.BIZ*.

    ![Captura de pantalla que muestra la página Agregar un dominio](media/direct-routing-2-sbc-add-domain.png)

3. Haga clic en **Siguiente**.
4. En el ejemplo, el inquilino ya tiene adatum.biz como un nombre de dominio verificado. El asistente no pedirá una verificación adicional porque customers.adatum.biz es un subdominio para el nombre que ya está registrado. Sin embargo, si agrega un FQDN que no se ha verificado antes, tendrá que pasar por el proceso de verificación. El proceso de verificación se [describe a continuación](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

    ![Captura de pantalla que muestra la confirmación de un nombre de dominio verificado](media/direct-routing-3-sbc-verify-domain.png)

5.  Haga clic en **siguiente**y, en la página **Actualizar configuración DNS** , seleccione **agregaré los registros DNS** y haga clic en **siguiente**.
6.  En la página siguiente, borre todos los valores (a menos que desee usar el nombre de dominio para Exchange, SharePoint o Teams/Skype empresarial), haga clic en **siguiente**y, a continuación, haga clic en **Finalizar**. Asegúrese de que el nuevo dominio se encuentra en el estado de instalación completada.

    ![Captura de pantalla que muestra los dominios con el estado de configuración completado](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Activar el nombre de dominio

Después de haber registrado un nombre de dominio, debe activarlo agregando al menos un usuario con licencia de E1, E3 o E5 y asignando una dirección SIP a la parte FQDN de la dirección SIP que coincide con el dominio base creado. 

*Para obtener más información sobre cómo agregar usuarios en Office 365 inquilinos, consulte [obtener ayuda con los dominios de office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

Por ejemplo: test@customers.adatum.biz

![Captura de pantalla de la página de activación del dominio básico](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrar un nombre de subdominio en un espacio empresarial de cliente

Tendrá que crear un nombre de subdominio único para cada cliente. En este ejemplo, crearemos un subdominio sbc1.customers.adatum.biz en un inquilino con el nombre de dominio predeterminado woodgrovebank.us.

**Todas las acciones siguientes se encuentran en el inquilino del cliente.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Asegurarse de que tiene los derechos adecuados en el inquilino del cliente

Solo puede agregar dominios nuevos si inició sesión en el centro de administración de Microsoft 365 como administrador global. 

Para validar el rol que tiene, inicie sesión en el centro de administración de Microsoft 365https://portal.office.com)(, vaya **** > a usuarios**activos**y, a continuación, compruebe que tiene un rol de administrador global. 

Para obtener más información acerca de los roles de administrador y cómo asignar un rol en Office 365, consulte [acerca de los roles de administrador de office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Agregar un subdominio al inquilino del cliente y comprobarlo
1. En el centro de administración de Microsoft 365, vaya a**dominios** > de **configuración** > **Agregar dominio**.
2. En el cuadro **Escriba un dominio** , escriba el FQDN del subdominio para este inquilino. En el ejemplo siguiente, el subdominio es sbc1.customers.adatum.biz.

    ![Captura de pantalla de la página Agregar un dominio](media/direct-routing-5-sbc-add-customer-domain.png)

3. Haga clic en **Siguiente**.
4. El FQDN nunca se ha registrado en el inquilino. En el siguiente paso, tendrá que comprobar el dominio. **En su lugar, seleccione Agregar un registro TXT**. 

    ![Captura de pantalla de la página comprobar dominio](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Haga clic en **siguiente**y anote el valor txt generado para comprobar el nombre de dominio.

    ![Captura de pantalla de registros de texto en la página comprobar dominio](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Cree el registro TXT con el valor del paso anterior en el proveedor de hospedaje DNS del operador.

    ![Captura de pantalla que muestra la creación del registro TXT](media/direct-routing-8-sbc-txt-record.png)

    Para obtener más información, consulte [crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Vuelva al centro de administración de Microsoft 365 del cliente y haga clic en **comprobar**. 
8. En la página siguiente, seleccione **voy a agregar los registros DNS** y haga clic en **siguiente**.

    ![Captura de pantalla de las opciones de la página actualizar la configuración DNS](media/direct-routing-9-sbc-update-dns.png)

9. En la página **elegir los servicios en línea** , desactive todas las opciones y haga clic en **siguiente**.

    ![Captura de pantalla de la página elegir los servicios en línea](media/direct-routing-10-sbc-choose-services.png)

10. Haga clic en **Finalizar** en la página **actualizar la configuración DNS** .

    ![Captura de pantalla de la página actualizar la configuración DNS](media/direct-routing-11-sbc-update-dns-finish.png)

11. Asegúrese de que el estado es de **configuración completada**. 
    
    ![Captura de pantalla de la página que muestra el estado de configuración completado](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>Activar el nombre del subdominio

Después de registrar un nombre de dominio, debe activarlo agregando al menos un usuario y asignarle una dirección SIP con la parte FQDN de la dirección SIP que coincide con el subdominio creado en el inquilino del cliente.

*Para obtener más información sobre cómo agregar usuarios en Office 365 inquilinos, consulte [obtener ayuda con los dominios de office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

Por ejemplo: test@sbc1.customers.adatum.biz

![Captura de pantalla de la activación de la página subdominio](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Crear un tronco y los usuarios de provisioning

Con la versión inicial del enrutamiento directo, Microsoft necesitaba un tronco que se agregara a cada inquilino servido (inquilino del cliente) con New-CSOnlinePSTNGateway.

Sin embargo, esto no ha sido óptimo por dos razones:
 
- **Gestión de gastos generales**. Al descargar o agotar un SBC, por ejemplo, cambian algunos parámetros, como habilitar o deshabilitar la omisión de medios. Cambiar el puerto requiere cambiar parámetros en varios inquilinos (ejecutando Set-CSOnlinePSTNGateway), pero en realidad es el mismo SBC. 

-  **Procesamiento de gastos generales**. Recopilar y supervisar los datos de estado de troncal: las opciones de SIP recopiladas de varios troncos lógicos, que son en realidad, el mismo SBC y el mismo tronco físico, ralentiza el procesamiento de los datos de enrutamiento.
 

Basándose en estos comentarios, Microsoft trae una nueva lógica para aprovisionar los troncos de los inquilinos de cliente.

Se introdujeron dos nuevas entidades:
-   Un tronco de portador registrado en el inquilino del operador usando el comando New-CSOnlinePSTNGateway, por ejemplo, New-CSOnlinePSTNGateway-FQDN customers.adatum.biz-SIPSignallingport 5068-ForwardPAI $true.

-   Un tronco derivado, que no requiere registro. Simplemente es un nombre de host deseado añadido desde el tronco del portador. Deriva todos sus parámetros de configuración del tronco del transportista. El tronco derivado no necesita crearse en PowerShell y la asociación con el tronco del portador se basa en el nombre de FQDN (vea los detalles a continuación).

**Lógica de aprovisionamiento y ejemplo**

-   Los operadores solo necesitan configurar y administrar un único tronco (tronco de portador en el dominio de la portadora) con el comando set-CSOnlinePSTNGateway. En el ejemplo anterior, es adatum.biz;
-   En el inquilino del cliente, el operador solo tiene que agregar el FQDN del tronco derivado a las directivas de enrutamiento de voz de los usuarios. No es necesario ejecutar New-CSOnlinePSTNGateway para un tronco.
-    El tronco derivado, como sugiere el nombre, hereda o deriva todos los parámetros de configuración del tronco del portador. Acerca
-   Customers.adatum.biz: el tronco del portador que debe crearse en el inquilino del transportista.
-   Sbc1.customers.adatum.biz: el tronco derivado de un inquilino de cliente que no tiene que crearse en PowerShell.  Simplemente puede Agregar el nombre del tronco derivado en el inquilino del cliente en la Directiva de enrutamiento de voz en línea sin crearlo.

-   Los cambios realizados en un tronco de portador (en el inquilino de transportista) se aplican automáticamente a los troncos derivados. Por ejemplo, los operadores pueden cambiar un puerto SIP en el tronco del portador, y este cambio se aplicará a todos los troncos derivados. La nueva lógica para configurar los troncos simplifica la administración, ya que no es necesario ir a cada inquilino y cambiar el parámetro en cada tronco.
-   Las opciones solo se envían al FQDN del tronco del transportista. El estado de mantenimiento del tronco del portador se aplica a todos los troncos derivados y se usa para las decisiones de enrutamiento. Más información sobre [las opciones de enrutamiento directo](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot).
-   El portador puede agotar el tronco del portador y todos los troncos derivados también se purgarán. 
 

**Migración del modelo anterior al tronco del portador**
 
Para la migración de la implementación actual del modelo hospedado por el portador al nuevo modelo, los operadores deberán volver a configurar los troncos para inquilinos de cliente. Elimine los troncos de los inquilinos del cliente mediante Remove-CSOnlinePSTNGateway (dejando el tronco en el inquilino del transportista):

Recomendamos encarecidamente migrar a la nueva solución tan pronto como sea posible, ya que mejoraremos la supervisión y el aprovisionamiento usando el modelo de tronco derivado y el portador.
 

Consulte las instrucciones de [proveedor de SBC](#deploy-and-configure-the-sbc) para configurar el envío del nombre de dominio completo de los subdominios en el encabezado de contacto.

