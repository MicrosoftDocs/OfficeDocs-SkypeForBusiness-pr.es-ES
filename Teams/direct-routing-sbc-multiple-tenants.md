---
title: 'Configurar el controlador de borde de sesión: varios espacios empresariales'
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar un controlador de borde de sesión (SBC) para que sirva a varios inquilinos para asociados de Microsoft o operadores RTC.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9d7ee3960f88b1c6ed4ee140b4f291162e37da30
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024023"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurar un controlador de borde de sesión para varios inquilinos

Direct Routing admite la configuración de un controlador de borde de sesión (SBC) para servir a varios espacios empresariales.

> [!NOTE]
> Este escenario está diseñado para asociados de Microsoft y/o operadores RTC, denominados operadores más adelante en este documento. Un operador vende servicios de telefonía entregados a Microsoft Teams a sus clientes. 

Un transportista:
- Implementa y administra un SBC en su centro de datos (los clientes no necesitan implementar un SBC y reciben servicios de telefonía del operador en el cliente de Teams).
- Interconecta el SBC a varios inquilinos.
- Proporciona servicios de red telefónica conmutada (RTC) a los clientes.
- Administra la calidad de la llamada de un extremo a otro.
- Cargos por separado para los servicios RTC.

Microsoft no administra los operadores. Microsoft ofrece sistema telefónico, una central de intercambio (PBX) y un cliente de Teams. Microsoft también certifica los teléfonos y los SBCs que se pueden usar con Phone System. Antes de elegir un operador, asegúrese de que su elección tiene un SBC certificado y puede administrar la calidad de voz de un extremo a otro.

A continuación se indican los pasos de implementación técnica para configurar el escenario.

**Solo carrier:**
1. Implemente el SBC y configúrelo para el escenario de hospedaje según [las instrucciones de los proveedores de SBC certificados](#deploy-and-configure-the-sbc).
2. Registre un nombre de dominio base en el inquilino del operador y solicite un certificado comodín.
3. Registre un subdominio para cada cliente, que forma parte del dominio base.

**Operador con un administrador global de clientes:**
1. Agregue el nombre de subdominio al inquilino del cliente.
2. Activar el nombre del subdominio.
3. Configure el tronco del operador al inquilino del cliente y aprovisione usuarios.

*Asegúrese de que comprende los conceptos básicos de DNS y cómo se administra el nombre de dominio en Microsoft 365. Consulte [Obtener ayuda con los dominios de Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) antes de continuar.*

## <a name="deploy-and-configure-the-sbc"></a>Implementar y configurar el SBC

Para conocer los pasos detallados sobre cómo implementar y configurar sbcs para un escenario de hospedaje SBC, consulte la documentación del proveedor de SBC.

- **Audiocodes:** Consulte [Notas de configuración de enrutamiento directo](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams) para obtener información sobre la configuración del escenario de hospedaje de SBC, tal y como se describe en "Conectar AudioCodes SBC a nota de configuración del modelo de hospedaje de enrutamiento directo de Microsoft Teams". 
- **Oracle:** Consulte [notas de configuración de enrutamiento directo](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html) para la configuración del escenario de hospedaje SBC, tal y como se describe en la sección "Microsoft". 
- **Comunicaciones de la cinta de opciones:** Consulte [Guía de configuración de Microsoft Teams de Ribbon Communications SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+MS+Teams+Solution+Guide) para obtener documentación sobre cómo configurar LOSC de Ribbon Core Series. Consulte también [Procedimientos recomendados de la cinta de opciones: Configuración de operadores para Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **TE-Systems (anynode):** Regístrese en el sitio de la [comunidad de TE-Systems](https://community.te-systems.de/) para obtener documentación y ejemplos sobre cómo configurar anynode SBC para varios inquilinos.
- **Metaswitch:** Regístrese en el sitio de la [comunidad de Metaswitch](https://manuals.metaswitch.com/MAN39555) para obtener documentación sobre cómo habilitar Perimeta SBC para varios inquilinos.

> [!NOTE]
> Asegúrese de que sabe cómo configurar el encabezado "Contacto". El encabezado Contacto se usa para buscar el inquilino del cliente en el mensaje de invitación entrante. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrar un dominio base y subdominios

Para el escenario de hospedaje, debe crear:

- Un nombre de dominio base propiedad del operador.
- Un subdominio que forma parte del nombre de dominio base en cada inquilino de cliente.

En el ejemplo siguiente:

- Adatum es una operadora que presta servicios de Telefonía e Internet a varios clientes.
- Woodgrove Bank, Contoso y Adventure Works son tres clientes que tienen dominios de Microsoft 365 pero que reciben los servicios de telefonía de Adatum.

Los subdominios **DEBEN** coincidir con el nombre FQDN del tronco que se configurará para el cliente y el FQDN en el encabezado Contacto al enviar la invitación a Microsoft 365. 

Cuando llega una llamada a la interfaz de Enrutamiento directo de Microsoft 365, la interfaz usa el encabezado de contacto para buscar el espacio empresarial en el que se debe buscar al usuario. Enrutamiento directo no usa la búsqueda de números de teléfono en la invitación, ya que es posible que algunos clientes tengan números no DID que se puedan superponer en varios inquilinos. Por lo tanto, el nombre fqdn en el encabezado de contacto es necesario para identificar el espacio empresarial exacto para buscar al usuario por el número de teléfono.

*Para obtener más información sobre cómo crear nombres de dominio en organizaciones de Microsoft 365, consulte [Obtener ayuda con los dominios de Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).*

En el siguiente diagrama se resumen los requisitos para basar el dominio, los subdominios y el encabezado De contacto.

:::image type="content" source="media/direct-routing-1-sbc-requirements.png" alt-text="Diagrama que muestra los requisitos para dominios y encabezado de contacto." lightbox="media/direct-routing-1-sbc-requirements.png":::

El SBC requiere un certificado para autenticar las conexiones. Para el escenario de hospedaje de SBC, el operador debe solicitar un certificado con CN y/o *SAN\* .base_domain (por ejemplo, \*.customers.adatum.biz)*. Este certificado se puede usar para autenticar conexiones a varios inquilinos servidos desde un único SBC.

La tabla siguiente es un ejemplo de una configuración.


|Nuevo nombre de dominio |Tipo|Registrado  |Certificado CN/SAN para SBC  |Dominio predeterminado del inquilino en el ejemplo  |Nombre FQDN que SBC debe incluir en el encabezado Contacto al enviar llamadas a usuarios|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base     |     Inquilino del operador  |    \*.customers.adatum.biz  |   adatum.biz      |NOD, este es un inquilino de servicio, no hay usuarios |
|sbc1.customers.adatum.biz|    Subdominio  |    En un inquilino de cliente  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Subdominio | En un inquilino de cliente   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Subdominio | En un inquilino de cliente |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |

Para configurar la base y los subdominios, siga los pasos que se describen a continuación. En este ejemplo se configura un nombre de dominio base (customers.adatum.biz) y un subdominio para un cliente (sbc1.customers.adatum.biz en el inquilino de Woodgrove Bank).

> [!NOTE]
> Use sbcX.customers.adatum.biz para habilitar la voz en el inquilino del operador; sbcX puede ser cualquier nombre de host alfanumérico único y válido.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registrar un nombre de dominio base en el inquilino del operador

**Estas acciones se realizan en el inquilino del operador.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Asegúrese de que tiene los derechos adecuados en el inquilino del transportista

Solo puede agregar nuevos dominios si inició sesión en la Centro de administración de Microsoft 365 como administrador global. 

Para validar el rol que tiene, inicie sesión en la Centro de administración de Microsoft 365 (https://portal.office.com), vaya a **Usuarios** > **activos** y, a continuación, compruebe que tiene un rol de administrador global. 

Para obtener más información sobre los roles de administrador y cómo asignar un rol en Microsoft 365, vea [Acerca de los roles de administrador](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Agregar un dominio base al inquilino y comprobarlo

1. En la Centro de administración de Microsoft 365, vaya a **Configuración** > **dominios** > **Agregar dominio**.

2. En el cuadro **Escriba un dominio de su propiedad** , escriba el FQDN del dominio base. En el ejemplo siguiente, se *customers.adatum.biz* el dominio base.

3. Haga clic en **Siguiente**.

4. En este ejemplo, el inquilino ya tiene adatum.biz como un nombre de dominio comprobado. El asistente no pedirá verificación adicional porque customers.adatum.biz es un subdominio del nombre ya registrado. Sin embargo, si agrega un FQDN que no se ha comprobado antes, tendrá que pasar por el proceso de verificación. El proceso de verificación se [describe a continuación](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

5. Seleccione **Siguiente** y, en la página **Actualizar configuración DNS** , seleccione **Agregaré los registros DNS y seleccionaré** **Siguiente**.

6. En la página siguiente, borre todos los valores (a menos que quiera usar el nombre de dominio para Exchange, SharePoint, Teams o Skype Empresarial), seleccione **Siguiente** y, después, **seleccione Finalizar**. Asegúrese de que el nuevo dominio está en el estado De instalación completa.

### <a name="activate-the-domain-name"></a>Activar el nombre de dominio

Después de registrar un nombre de dominio, debe activarlo agregando al menos una cuenta de usuarios o recursos con licencia de Teams. Las cuentas aceptables se licenciarán con cualquiera de las siguientes SKU:

- Cuenta de usuario con Office 365 E1/E3/E5/A3/A5 o Microsoft 365 E3/E5/A3/A5
- Cuenta de usuario con Office 365 F1/F3 o Microsoft 365 F1/F3
- Cuenta de usuario con teléfono de área común
- Cuenta de recursos con licencia **de cuenta de recursos de Teléfono Microsoft Teams**

Además, el UPN (nombre principal de usuario) de la cuenta o Skype Empresarial dirección SIP local debe usar el mismo FQDN que el dominio recién creado.

Para obtener más información sobre cómo agregar usuarios en organizaciones de Microsoft 365, consulte [Obtener ayuda con los dominios de Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Por ejemplo: test@customers.adatum.biz

![Captura de pantalla de la página de activación de dominio base.](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrar un nombre de subdominio en un inquilino de cliente

Tendrá que crear un nombre de subdominio único para cada cliente. En este ejemplo, crearemos un sbc1.customers.adatum.biz de subdominio en un inquilino con el nombre de dominio predeterminado woodgrovebank.us.

**Todas las acciones siguientes se encuentran en el inquilino del cliente.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Asegúrese de que tiene los derechos adecuados en el inquilino del cliente

Solo puede agregar nuevos dominios si inició sesión en la Centro de administración de Microsoft 365 como administrador global. 

Para validar el rol que tiene, inicie sesión en la Centro de administración de Microsoft 365 (https://portal.office.com), vaya a **Usuarios** > **activos** y, a continuación, compruebe que tiene un rol de administrador global. 

Para obtener más información sobre los roles de administrador y cómo asignar un rol en Microsoft 365, vea [Acerca de los roles de administrador](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Agregar un subdominio al inquilino del cliente y comprobarlo

1. En la Centro de administración de Microsoft 365, vaya a **Configuración** > **dominios** > **Agregar dominio**.

2. En el cuadro **Escriba un dominio de su propiedad** , escriba el FQDN del subdominio para este inquilino. En el ejemplo siguiente, el subdominio está sbc1.customers.adatum.biz.

3. Seleccione **Siguiente**.

4. El FQDN nunca se ha registrado en el inquilino. En el paso siguiente, tendrá que comprobar el dominio. Seleccione **Agregar un registro TXT en su lugar**. 

5. Seleccione **Siguiente** y anote el valor TXT generado para comprobar el nombre de dominio.

    ![Captura de pantalla de registros de texto en la página Comprobar dominio.](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Cree el registro TXT con el valor del paso anterior en el proveedor de host DNS del operador.

    Para obtener más información, vea [Crear registros DNS en cualquier proveedor de host DNS](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Ve al Centro de administración de Microsoft 365 del cliente y selecciona **Comprobar**. 

8. En la página siguiente, seleccione **Agregaré los registros DNS yo mismo** y **seleccionaré Siguiente**.

9. En la página **Elegir el servicios en línea**, desactive todas las opciones y seleccione **Siguiente**.

10. Seleccione **Finalizar** en la página **Actualizar configuración DNS** .

11. Asegúrese de que el estado es **Configuración completada**.

    ![Captura de pantalla de la página que muestra el estado del programa de instalación completado.](media/direct-routing-12-sbc-setup-complete.png)

> [!NOTE]
> La dirección URL base y el subdominio del cliente individual tienen que estar en el mismo espacio empresarial para permitirle agregar un tronco de _ruta directa_ .

### <a name="activate-the-subdomain-name"></a>Activar el nombre del subdominio

Después de registrar un nombre de subdominio, debe activarlo agregando al menos una cuenta de usuarios o recursos con licencia de Teams. Las cuentas aceptables se licenciarán con cualquiera de las siguientes SKU:

-   Cuenta de usuario con Office 365 E1/E3/E5/A3/A5 o Microsoft 365 E3/E5/A3/A5
-   Cuenta de usuario con Office 365 F1/F3 o Microsoft 365 F1/F3
-   Cuenta de usuario con teléfono de área común
-   Cuenta de recursos con una licencia de **cuenta de recursos de Teléfono Microsoft Teams**

Además, el UPN (nombre principal de usuario) de la cuenta o Skype Empresarial dirección SIP local debe usar el mismo FQDN que el subdominio recién creado.

Para obtener más información sobre cómo agregar usuarios en organizaciones de Microsoft 365, consulte [Obtener ayuda con Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Por ejemplo: test@sbc1.customers.adatum.biz

![Captura de pantalla de la página Activación del subdominio.](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Crear un tronco y aprovisionar usuarios

Con la versión inicial de Enrutamiento directo, Microsoft requería que se agregara un tronco a cada inquilino servido (inquilino del cliente) mediante el cmdlet New-CSOnlinePSTNGateway.

Sin embargo, este método no ha demostrado ser óptimo por dos razones:
 
- **Gestión de gastos generales**. La descarga o el drenaje de un SBC, por ejemplo, cambia algunos parámetros, como habilitar o deshabilitar la omisión de medios. Cambiar el puerto requiere cambiar parámetros en varios espacios empresariales (ejecutando Set-CSOnlinePSTNGateway), pero de hecho es el mismo SBC. 

-  **Procesamiento de gastos generales**. Recopilación y supervisión de datos de estado del tronco - opciones SIP recopiladas de múltiples troncos lógicos que son, en realidad, el mismo SBC y el mismo tronco físico, ralentiza el procesamiento de los datos de ruteo.
 
Basándose en estos comentarios, Microsoft está incorporando una nueva lógica para aprovisionar los troncos para los inquilinos de clientes.

Se introdujeron dos nuevas entidades:

- Tronco de operador registrado en el inquilino del operador mediante el comando New-CSOnlinePSTNGateway. Por ejemplo: 
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

- Tronco derivado que no requiere registro. Es simplemente un nombre de host deseado agregado desde el tronco del portador. Deriva todos sus parámetros de configuración del tronco del portador. La asociación con el tronco del operador se basa en el nombre fqdn (consulte los detalles abajo).

**Ejemplo y lógica de aprovisionamiento**

- Los operadores necesitan configurar y administrar solamente un único tronco (el tronco del portador en el dominio del portador) usando el comando Set-CSOnlinePSTNGateway. En el ejemplo anterior es adatum.biz.

- En el inquilino del cliente, el operador necesita agregar el FQDN del tronco derivado a las rutas de voz. No hay necesidad de ejecutar New-CSOnlinePSTNGateway para un tronco.

- El tronco derivado, como el nombre sugiere, hereda o deriva todos los parámetros de configuración del tronco del portador. 

Ejemplos:
- Customers.adatum.biz: el tronco del transportista que debe crearse en el inquilino del transportista.

- Sbc1.customers.adatum.biz: el tronco derivado en un inquilino de cliente. Puede agregar el nombre del tronco derivado en el inquilino del cliente en las rutas de voz sin crearlo.

- El operador tendrá que configurar el registro DNS que resuelve el FQDN del tronco derivado a la dirección IP SBC del operador.

- Cualquier cambio realizado en un tronco del transportista (en el inquilino del operador) se aplica automáticamente a los troncos derivados. Por ejemplo, los operadores pueden cambiar un puerto SIP en el tronco del portador, y este cambio se aplica a todos los troncos derivados. La nueva lógica para configurar los troncos simplifica la administración ya que no necesita ir a cada inquilino y cambiar el parámetro en cada tronco.

- Las opciones se envían solo al FQDN del tronco del transportista. El estado de mantenimiento del tronco del portador se aplica a todos los troncos derivados y se utiliza para las decisiones de ruteo. Obtenga más información sobre las [opciones de enrutamiento directo](./direct-routing-monitor-and-troubleshoot.md).

- El portador puede drenar el tronco del portador, y todos los troncos derivados serán drenados también. 
 
> [!NOTE]
> Las reglas de traducción de números aplicadas en el tronco del transportista no se aplican a los troncos derivados. Este es un problema conocido. Como solución alternativa, se deben crear reglas de traducción de números para el inquilino de cada cliente.

**Migración del modelo anterior al tronco del transportista**
 
Para la migración desde la implementación actual del modelo hospedado del operador al nuevo modelo, los operadores tendrán que volver a configurar los troncos para los inquilinos del cliente. Quite los troncos de los inquilinos del cliente mediante Remove-CSOnlinePSTNGateway (dejando el tronco en el inquilino del transportista)-

Recomendamos encarecidamente migrar a la nueva solución tan pronto como sea posible, ya que mejoraremos la supervisión y el aprovisionamiento mediante el operador y el modelo de tronco derivado.
 
Para obtener más información sobre cómo configurar el envío del nombre FQDN de subdominios en el encabezado Contacto, vea las [instrucciones del proveedor de SBC](#deploy-and-configure-the-sbc).

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>Consideraciones para configurar la conmutación por error de varios espacios empresariales 

Para configurar la conmutación por error en un entorno multiempresa, debe hacer lo siguiente:

- Para cada inquilino, agregue los FQDN para dos SBCs diferentes. Por ejemplo:

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- En Rutas de voz en línea, especifique ambos SBCs. Si se produce un error en un SBC, la directiva de enrutamiento enrutará las llamadas al segundo SBC.


## <a name="see-also"></a>Vea también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)
