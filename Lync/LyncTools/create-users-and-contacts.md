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
ms.openlocfilehash: f30737ebf721d17059418c690e678f69f0296a6c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a>Crear usuarios y contactos

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Debe usar la herramienta de aprovisionamiento de usuarios de Lync Server 2013 (UserProvisioningTool. exe) para crear usuarios y contactos para preparar la prueba de carga de rendimiento y estrés.

A continuación, se incluye una lista de términos y definiciones que puede resultarle útil a la lectura de este tema.

  - Unidad organizativa: la unidad organizativa (Uo) de los servicios de dominio de Active Directory.

  - Federado/grupo cruzado: usuarios que se habilitarán para comunicarse con usuarios de otros servicios de mensajería instantánea (mi), como MSN Network of Internet Services, AOL® y Yahoo\!®.

  - Listas de distribución: objetos de los servicios de dominio de Active Directory que contienen una lista de usuarios de los servicios de dominio de Active Directory, que se usan para iniciar comunicaciones con grupos de personas.

  - Servicio de información de Ubicación: el servicio Lync Server 2013 que, cuando se habilitan y configuran por teléfono, permite la recuperación de la ubicación física para los servicios mejorados 9-1-1 (E9-1-1).

  - Números de teléfono de Estados Unidos: los números de teléfono asignados a los usuarios, además del URI de SIP que se usa para enrutar las llamadas entrantes y salientes, y la búsqueda inversa de números (RNL).

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Crear usuarios y contactos con UserProvisioningTool. exe

Debe usar la herramienta de aprovisionamiento de usuarios de Lync Server para crear usuarios y contactos para la simulación de carga. La herramienta de aprovisionamiento de usuarios de Lync Server se instala con el paquete de la herramienta de esfuerzo y rendimiento de Lync Server. Asegúrese de que el instalador del paquete (CapacityPlanningTool. msi) se ha ejecutado en el servidor front-end o en el servidor Standard Edition. Inicie la herramienta de aprovisionamiento de usuarios de Lync Server; para ello, ejecute el archivo UserProvisioningTool. exe (que se\\encuentra en% InstalledDirectory% LyncStressAndPerfTool LyncStress) en el servidor front-end o en el servidor Standard Edition.

<div>


> [!IMPORTANT]  
> Debe haber iniciado sesión como miembro del grupo de seguridad administradores de dominio para poder ejecutar UserProvisioningTool. exe. Es necesario ejecutar desde este contexto porque UserProvisioningTool. exe creará y configurará nuevos usuarios de los servicios de dominio de Active Directory.



</div>

<div>


> [!NOTE]  
> Cuando cree un número significativo de usuarios (de 10.000 o más), ejecute UserProvisioningTool. exe desde un equipo de gama alta. Tenga en cuenta que el controlador de dominio también experimentará una carga elevada mientras se crean los usuarios.



</div>

Cuando se abra la herramienta de aprovisionamiento de usuarios de Lync Server, haga clic en **configuración** y seleccione **cargar configuración**. Para empezar a configurar usuarios y contactos, cargue el archivo predeterminado que se incluye en el paquete, SampleData. Xml. Esto rellenará previamente los campos con datos de ejemplo que necesitará revisar en el sistema. Si tiene un archivo XML preconfigurado que ya contiene una configuración personalizada, cargue ese archivo en su lugar. Rellene los campos de la herramienta de aprovisionamiento de usuarios de Lync Server, tal y como se describe en las secciones siguientes.

![Pestaña creación de usuario.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Pestaña creación de usuario.")

Para configurar las opciones del servidor, siga estos pasos.

1.  En **FQDN del grupo de servidores front-end**, escriba el nombre de dominio completo (FQDN) del servidor Standard Edition o del grupo de servidores front-end en el que desea hospedar a los usuarios.

2.  En **Prefijo de nombre de usuario**, escriba un prefijo que desee usar para crear nombres de usuario con fines de prueba.

3.  En **contraseña**, especifique una contraseña que se aplicará a todas las cuentas de usuario de prueba.

4.  En **dominio SIP**, escriba el nombre de dominio que se usará para los URI del SIP de los usuarios de prueba (identificadores uniformes de recursos).

5.  En **dominio de cuenta**, escriba el nombre de dominio de su dominio de servicios de dominio de Active Directory actual, en el que desea crear los usuarios de prueba.

6.  En **unidad organizativa**, escriba el nombre de la unidad organizativa de los servicios de dominio de Active Directory donde desea crear los objetos de usuario. Si la unidad organizativa no existe, se creará.

7.  En **código de área de teléfono**, escriba el código de área de tres dígitos que se usará para las cuentas de usuario de prueba. Asegúrese de que el código de área de teléfono no entre en conflicto con otros códigos de área de los servicios de dominio de Active Directory.

8.  Active la casilla de verificación **voz habilitada** si desea habilitar a los usuarios de prueba para telefonía IP empresarial.

9.  En **número de usuarios**, especifique el número total de usuarios de prueba que desea crear.

10. En **iniciar índice**, especifique el número inicial que se utilizará como sufijo en el prefijo del nombre de usuario.

<div>

## <a name="create-users-button"></a>Botón crear usuarios

Al hacer clic en el botón crear usuarios, se validarán todos los parámetros de entrada.

  - Si hay errores de validación, se le pedirá que corrija los valores de entrada.

  - Si todos los valores de entrada son correctos, empezará a crear usuarios en los servicios de dominio de Active Directory. Aparecerá una barra de progreso en la parte inferior de este formulario. Le recomendamos que no cierre la aplicación mientras está activa la barra de progreso.

La creación de usuarios es un proceso lento. Puede tardar varios minutos. Si el número de usuarios es muy grande, el proceso podría tardar unas pocas horas. Si los usuarios ya existen, se actualizan con los cambios. Puede validar que los usuarios se han creado iniciando sesión como uno de los usuarios del intervalo. Use el prefijo de usuario, el número de usuario y @sipDomain como nombre de usuario (por ejemplo, LyncUser10@contoso.net), junto con la contraseña especificada.

</div>

<div>

## <a name="delete-users-button"></a>Botón eliminar usuarios

Al hacer clic en el botón eliminar usuarios, se validarán todos los parámetros de entrada.

  - Si hay errores de validación, se le pedirá que corrija los valores de entrada.

  - Si todos los valores de entrada son correctos, empezará a deshabilitar y eliminar usuarios en servicios de dominio de Active Directory. Aparecerá una barra de progreso en la parte inferior de este formulario. Le recomendamos que no cierre la aplicación mientras está activa la barra de progreso.

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>Solo se admiten números de teléfono con formato estadounidense. Los números de teléfono se asignan siempre a los usuarios y todos los usuarios creados por UserProvisioningTool. exe están habilitados para telefonía IP empresarial. Los escenarios que usan el número de teléfono, como el operador automático de conferencia o las llamadas de UC-RTC, usan este número de teléfono para enrutar las llamadas correctamente. Por este motivo, todos los usuarios deben tener un número de teléfono único. Si tiene que crear dos veces usuarios, se producirá un error en el comando a menos que use otro código de área o si los usuarios anteriores se han deshabilitado mediante el cmdlet <STRONG>Disable-CsUser</STRONG> .</P>
> <LI>
> <P>Antes de crear contactos, debe completar primero la replicación de usuario, que se realiza desde la pestaña usuarios. Si acaba de crear los usuarios, debe esperar hasta que se complete la replicación de Lync Server y se llenen las cuentas de usuario de la base de datos. Si los usuarios no han terminado de replicarse, verá un error. Sabrá Cuándo los usuarios han terminado de replicarse si se ha iniciado el servicio front-end de Lync Server 2013 o si se ha ejecutado correctamente el cmdlet <STRONG>Get-CsUser</STRONG> en el último usuario.</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>Pestaña creación de contactos

La ficha creación de contactos le permite especificar los detalles de los contactos de los usuarios.

![Pestaña creación de contactos.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Pestaña creación de contactos.")

Para configurar los contactos de los usuarios, siga estos pasos.

1.  En promedio de contactos por usuario, especifique el número medio de contactos que se van a rellenar en las listas de contactos de cada uno de los usuarios.

2.  Active la casilla de verificación fijo Si desea crear un número igual de contactos para cada usuario. Si desea variar el número de contactos creados para los usuarios, desactive la casilla.

3.  En grupos de contactos promedio por usuario, especifique el número de grupos de contactos por usuario. Este número debe ser menor que el promedio de contactos por usuario.

4.  En porcentaje de contactos de Federated/Cross pools, especifique un número entre 0 y 100. Este porcentaje de contactos se creará con los usuarios federados.

5.  En el prefijo de usuario de federado/grupo cruzado, especifique el nombre de usuario para los usuarios federados que se agregarán a las listas de contactos de los usuarios locales.

6.  En dominio SIP de usuario federado/grupo cruzado, especifique el nombre de dominio SIP de los usuarios federados.
    
    <div>
    

    > [!NOTE]  
    > Ninguno de los usuarios debe iniciar sesión al crear contactos.

    
    </div>

7.  En la ficha creación de usuario, compruebe que los parámetros son correctos. El rango de usuarios para los que se crearán los contactos se obtiene de la pestaña creación de usuarios.

8.  Haga clic en crear contactos para iniciar la creación de contactos. Este proceso puede tardar varios minutos. Una vez finalizado, aparecerá un cuadro de diálogo con el mensaje "la operación se completó correctamente". Puede validar los contactos que se crearon iniciando sesión como un usuario que se creó desde la pestaña creación de usuarios.
    
    <div>
    

    > [!NOTE]  
    > Una vez creados los contactos, esta herramienta reiniciará todos los servidores front-end del grupo de servidores de destino. Los servidores front-end pueden tardar más tiempo (hasta 2 horas) en iniciarse, en función de cuántos contactos haya creado esta operación.

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>Lista de distribución

Una de las características de la herramienta stress and performance de Lync Server 2013 es simular la característica de expansión de la lista de distribución (DL) en Lync 2013. Si no va a habilitar la expansión de DL en UserProvisioningTool, puede omitir este paso.

![Ficha creación de lista de distribución.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Ficha creación de lista de distribución.")

La ficha Lista de distribución le permite crear listas de distribución que la herramienta stress and Performance usará para la característica de expansión de listas de distribución. Antes de crear las listas de distribución, es necesario que Lync Server 2013 ya esté instalado. Debe haber ejecutado Lync Server 2013 ForestPrep. De lo contrario, los atributos DL no existen en el esquema de servicios de dominio de Active Directory y la herramienta no podrá crear listas de distribución.

Para configurar listas de distribución, siga estos pasos.

1.  En número de listas de distribución, especifique el número total de DL que desea crear. (Le recomendamos que empiece con el doble del número de usuarios). Se numeran de 0 a n-1.

2.  En Prefijo de lista de distribución, especifique el prefijo que tendrá la DL. Por ejemplo, si especifica 100 DLs y un prefijo de testDL, las listas de distribución recibirán el nombre testDL0, testDL1, etc., a través de testDL99.

3.  En miembros mínimos de una lista Dist., especifique el número mínimo de usuarios que se agregarán en cada lista de distribución.

4.  En número máximo de miembros de una lista de distribución, especifique el número máximo de usuarios que se agregarán en cada lista de distribución.

<div>

## <a name="create-distribution-lists-button"></a>Botón crear listas de distribución

Al hacer clic en el botón crear listas de distribución, la herramienta consulta servicios de dominio de Active Directory para ver si las listas de distribución que coinciden con el prefijo y los números ya existen. La herramienta solo creará las que aún no existen. Cuando se agregan miembros a estas listas de distribución recién creadas, se seleccionan los usuarios del rango especificado en la pestaña creación de usuarios.

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>Ficha Configuración del servicio de información de ubicación

Una de las características de la herramienta de esfuerzo y rendimiento de Lync Server 2013 es generar archivos de configuración ficticio para el servicio de información de ubicación. El servicio de información de ubicación no suele tener un impacto significativo en el rendimiento de los servidores.

![Ficha Configuración del servicio de información de ubicación.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Ficha Configuración del servicio de información de ubicación.")

Si elige probar esta característica, puede rellenar los valores mencionados en el formulario y, a continuación, hacer clic en el botón generar archivos de configuración de LIS. Se generarán archivos CSV denominados\_subred Lis. csv,\_modificadores Lis. csv\_, puertos Lis. csv y\_Lis. csv de lis. A continuación, puede importar estos archivos CSV a la base de datos de LIS mediante el cmdlet **set-CsLisSubnet** , el cmdlet **set-CsLisSwitch** , el cmdlet **set-CsLisPort** y el cmdlet **set-CsWirelessAccessPoint** , respectivamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

