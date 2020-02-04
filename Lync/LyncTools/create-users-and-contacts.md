---
title: Crear usuarios y contactos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1463a7caaad2bcf36996eaac4bd47e2bab25e6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a>Crear usuarios y contactos

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Debe usar la herramienta de aprovisionamiento de usuarios de Lync Server 2013 (UserProvisioningTool. exe) para crear usuarios y contactos como preparación para pruebas de carga de rendimiento y estrés.

Esta es una lista de términos y definiciones que puede que le resulte útil a la lectura de este tema.

  - Unidad organizativa: la unidad organizativa de los servicios de dominio de Active Directory.

  - Federado/grupo cruzado: usuarios que se habilitarán para comunicarse con los usuarios de otros servicios de mensajería instantánea (mi), como la red MSN de servicios de Internet, AOL®\!y Yahoo®.

  - Listas de distribución: los objetos de los servicios de dominio de Active Directory que contienen una lista de usuarios de los servicios de dominio de Active Directory, que se usan para iniciar las comunicaciones con grupos de personas.

  - Servicio de información de Ubicación: servicio de Lync Server 2013 que, cuando se habilitan y configuran por teléfono, permite la recuperación de la ubicación física de los servicios de 9-1-1 (E9-1-1) mejorados.

  - Números de teléfono de Estados Unidos: números de teléfono que se asignan a los usuarios, además del URI de SIP que se usa para el enrutamiento de llamadas entrantes y salientes, y búsqueda inversa de números (RNL).

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Crear usuarios y contactos con UserProvisioningTool. exe

Debe usar la herramienta de aprovisionamiento de usuarios de Lync Server para crear usuarios y contactos para simulación de carga. La herramienta de aprovisionamiento de usuarios de Lync Server se instala con el paquete de herramientas de estrés y rendimiento de Lync Server. Asegúrese de que el instalador del paquete (CapacityPlanningTool. msi) se ha ejecutado en el servidor front-end o en el servidor Standard Edition. Inicie la herramienta de aprovisionamiento de usuarios de Lync Server ejecutando el archivo UserProvisioningTool. exe (que se encuentra en% InstalledDirectory\\% LyncStressAndPerfTool LyncStress) en el servidor front-end o en el servidor Standard Edition.

<div>


> [!IMPORTANT]  
> Para ejecutar UserProvisioningTool. exe, debe haber iniciado sesión como miembro del grupo de seguridad administradores del dominio. Es necesario ejecutarlo desde este contexto porque UserProvisioningTool. exe creará y configurará nuevos usuarios de los servicios de dominio de Active Directory.



</div>

<div>


> [!NOTE]  
> Cuando cree un número significativo de usuarios (10.000 o más), ejecute UserProvisioningTool. exe desde un equipo de gama alta. Tenga en cuenta que el controlador de dominio también experimentará una carga elevada mientras se crean los usuarios.



</div>

Cuando se abra la herramienta de aprovisionamiento de usuarios de Lync Server, haga clic en **configuración** y seleccione **cargar configuración**. Para empezar a configurar usuarios y contactos, cargue el archivo predeterminado que se incluye en el paquete, SampleData. Xml. Esto rellenará previamente los campos con datos de ejemplo que necesitará revisar para su sistema. Si tiene un archivo XML preconfigurado que ya contiene una configuración personalizada, cargue ese archivo en su lugar. Rellene los campos de la herramienta de aprovisionamiento de usuarios de Lync Server, tal y como se describe en las secciones siguientes.

![Pestaña de creación de usuarios.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Pestaña de creación de usuarios.")

Para configurar las opciones del servidor, siga estos pasos.

1.  En **FQDN del grupo de servidores front end**, escriba el nombre de dominio completo (FQDN) del servidor Standard Edition o del grupo de servidores front-end en el que desea hospedar a los usuarios.

2.  En **Prefijo de nombre de usuario**, escriba un prefijo que desee usar para crear nombres de usuario con el fin de realizar pruebas.

3.  En **contraseña**, especifique una contraseña que se aplicará a todas las cuentas de usuario de prueba.

4.  En **dominio SIP**, escriba el nombre de dominio que se usará para los URI del SIP de los usuarios de prueba (identificadores uniformes de recursos).

5.  En **dominio**de la cuenta, escriba el nombre de dominio de su dominio de servicios de dominio de Active Directory actual, en el que desea crear los usuarios de prueba.

6.  En **unidad organizativa**, escriba el nombre de la UO de los servicios de dominio de Active Directory donde desea crear los objetos de usuario. Si la OU no existe, se creará.

7.  En **código de área**, escriba el código de área de tres dígitos que se usará para las cuentas de usuario de prueba. Asegúrese de que el código de área de teléfono no entra en conflicto con los códigos de área de otros usuarios de los servicios de dominio de Active Directory.

8.  Active la casilla de verificación **voz habilitada** si desea habilitar los usuarios de prueba para telefonía IP empresarial.

9.  En **número de usuarios**, especifique el número total de usuarios de prueba que desea crear.

10. En **Índice de inicio**, especifique el número inicial que se usará como sufijo para el prefijo del nombre de usuario.

<div>

## <a name="create-users-button"></a>Botón crear usuarios

Al hacer clic en el botón crear usuarios, se validan todos los parámetros de entrada.

  - Si hay algún error de validación, se le pedirá que corrija esos valores de entrada.

  - Si todos los valores de entrada son correctos, comenzará a crear usuarios en servicios de dominio de Active Directory. Aparecerá una barra de progreso en la parte inferior de este formulario. Le recomendamos que no cierre la aplicación mientras la barra de progreso esté activa.

La creación de usuarios es un proceso lento. Puede demorar varios minutos. Si el número de usuarios es muy grande, el proceso puede demorar incluso unas pocas horas. Si los usuarios ya existen, se actualizan con los cambios. Puede validar que los usuarios se hayan creado iniciando sesión como uno de los usuarios del rango. Use el prefijo de usuario, el número de usuario y @sipDomain como nombre de usuario (por ejemplo, LyncUser10@contoso.net), junto con la contraseña especificada.

</div>

<div>

## <a name="delete-users-button"></a>Botón eliminar usuarios

Al hacer clic en el botón eliminar usuarios, se validan todos los parámetros de entrada.

  - Si hay algún error de validación, se le pedirá que corrija esos valores de entrada.

  - Si todos los valores de entrada son correctos, empezará a deshabilitar y eliminar usuarios en servicios de dominio de Active Directory. Aparecerá una barra de progreso en la parte inferior de este formulario. Le recomendamos que no cierre la aplicación mientras la barra de progreso esté activa.

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>Solo se admiten números de teléfono con formato estadounidense. Los números de teléfono siempre se asignan a los usuarios y todos los usuarios creados por UserProvisioningTool. exe están habilitados para telefonía IP empresarial. Cualquier escenario que use el número de teléfono, como el operador automático de la Conferencia o las llamadas UC-RTC, use este número de teléfono para enrutar las llamadas correctamente. Por esta razón, todos los usuarios deben tener un número de teléfono único. Si tiene que crear dos veces usuarios, el comando fallará a menos que use un código de área diferente o si los usuarios anteriores se han deshabilitado mediante el cmdlet <STRONG>Disable-CsUser</STRONG> .</P>
> <LI>
> <P>Antes de crear contactos, primero debe completar la replicación de usuario, desde la ficha usuarios. Si acaba de crear los usuarios, debe esperar hasta que se complete la replicación de Lync Server y se llenen las cuentas de usuario de la base de datos. Si los usuarios no han terminado de replicarse, verá un error. Sabrá Cuándo los usuarios han terminado de replicar si el servicio de front-end de Lync Server 2013 se ha iniciado o si ejecuta correctamente el cmdlet <STRONG>Get-CsUser</STRONG> en el último usuario.</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>Ficha creación de contactos

La ficha creación de contactos le permite especificar los detalles de los contactos de los usuarios.

![Pestaña de creación de contactos.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Pestaña de creación de contactos.")

Para configurar los contactos de los usuarios, siga estos pasos.

1.  En promedio de contactos por usuario, especifique la cantidad promedio de contactos que se van a rellenar en las listas de contactos de cada uno de los usuarios.

2.  Seleccione la casilla fijo Si desea crear un número igual de contactos para cada usuario. Si desea variar el número de contactos creados para los usuarios, desactive la casilla.

3.  En promedio de grupos de contactos por usuario, especifique el número de grupos de contactos por usuario. Este número debe ser menor que el promedio de contactos por usuario.

4.  En el porcentaje de contactos federado/grupo cruzado, especifique un número entre 0 y 100. Este porcentaje de contactos se creará con los usuarios federados.

5.  En el prefijo de usuario federado/grupo cruzado, especifique el nombre de usuario de los usuarios federados que se agregará a las listas de contactos de los usuarios locales.

6.  En dominio SIP de usuario federado/grupo cruzado, especifique el nombre de dominio SIP de los usuarios federados.
    
    <div>
    

    > [!NOTE]  
    > Ninguno de los usuarios debe haber iniciado sesión al crear contactos.

    
    </div>

7.  En la ficha creación de usuario, compruebe que los parámetros son correctos. El intervalo de usuarios para los que se crearán los contactos se obtiene de la pestaña creación de usuarios.

8.  Haga clic en crear contactos para comenzar la creación de contactos. Este proceso puede demorar varios minutos. Una vez completada, aparecerá un cuadro de diálogo con el mensaje "la operación se completó correctamente". Puede validar los contactos que se crearon iniciando sesión como un usuario creado desde la pestaña creación de usuarios.
    
    <div>
    

    > [!NOTE]  
    > Una vez que se crean los contactos, esta herramienta reiniciará todos los servidores front-end en el grupo de destino. Es posible que se tarde más (hasta 2 horas) en iniciarse los servidores front-end, dependiendo de cuántos contactos haya creado esta operación.

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>Lista de distribución

Una de las características de la herramienta de rendimiento y estrés de Lync Server 2013 es simular la característica de expansión de la lista de distribución (DL) en Lync 2013. Si no va a habilitar la expansión de DL en UserProvisioningTool, puede omitir este paso.

![Pestaña de creación de listas de distribución.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Pestaña de creación de listas de distribución.")

La pestaña lista de distribución le permite crear listas de distribución que la herramienta esfuerzo y rendimiento usará para la característica de expansión de la lista de distribución. Antes de crear las listas de distribución, Lync Server 2013 debe estar instalado. Debe tener instalado ForestPrep de Lync Server 2013. En caso contrario, los atributos de DL no existen en el esquema de los servicios de dominio de Active Directory y la herramienta no podrá crear listas de distribución.

Para configurar listas de distribución, siga estos pasos.

1.  En número de listas de distribución, especifique el número total de listas de distribución que desea crear. (Le recomendamos que comience con el doble de usuarios). Se numeran de 0 a n-1.

2.  En Prefijo de lista de distribución, especifique el prefijo que tendrá la lista de distribución. Por ejemplo, si especifica 100 DLs y un prefijo de testDL, las listas de distribución se denominarán testDL0, testDL1 y así sucesivamente, a través de testDL99.

3.  En la lista de miembros mínimos de una lista de distribución, especifique el número mínimo de usuarios que desea agregar en cada lista de distribución.

4.  En máximo de miembros de una lista DISTR., especifique el número máximo de usuarios que desea agregar en cada lista de distribución.

<div>

## <a name="create-distribution-lists-button"></a>Botón crear listas de distribución

Al hacer clic en el botón crear listas de distribución, la herramienta consulta servicios de dominio de Active Directory para ver si ya existen listas de distribución que coincidan con el prefijo y los números. La herramienta creará solo las que aún no existen. Al agregar miembros a estas listas de distribución recién creadas, se seleccionarán los usuarios del rango especificado en la pestaña creación de usuarios.

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>Ficha Configuración del servicio de información de ubicación

Una de las características de la herramienta Lync Server 2013 stress and performance es generar archivos de configuración ficticios para el servicio de información de ubicación. El servicio de información de ubicación normalmente no tiene ningún impacto significativo en el rendimiento de los servidores.

![Pestaña de configuración del servicio de información de ubicación.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Pestaña de configuración del servicio de información de ubicación.")

Si elige probar esta característica, puede rellenar los valores mencionados en el formulario y, a continuación, hacer clic en el botón generar archivos de configuración de LIS. Generará archivos CSV llamados subred LIS\_. csv, conmutadores\_Lis. csv, puertos\_Lis. csv y Lis\_. csv de lis. Después, puede importar estos archivos CSV en la base de datos de LIS con el cmdlet **set-CsLisSubnet** , el cmdlet Set **-CsLisSwitch** , el cmdlet **set-CsLisPort** y el cmdlet **set-CsWirelessAccessPoint** , respectivamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

