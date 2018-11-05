---
title: "Requisitos DNS para inicio de sesión automática del cliente en Lync Server 2013"
TOCTitle: "Enr. DNS requis pour la connexion auto. des clients dans Lync Server 2013"
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48274994
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos DNS para inicio de sesión automática del cliente en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En esta sección se describen los registros del sistema de nombres de dominio (DNS) necesarios para el inicio de sesión automático de clientes. Cuando se implementan servidores Standard Edition o grupos de servidores front-end, se pueden configurar los clientes para que usen la detección automática para iniciar sesión en el servidor Standard Edition o el grupo de servidores front-end adecuado. Si piensa exigir que los clientes se conecten manualmente a Lync Server 2013, puede omitir este tema.

Para admitir el inicio de sesión automático de los clientes, debe:

  - Designar un único servidor o grupo de servidores para distribuir y autenticar las solicitudes de inicio de sesión de los clientes. Puede ser uno de los servidores o grupos de servidores existentes en la organización que hospede usuarios, o bien, puede designar un servidor o grupo de servidores dedicado para este fin que no hospede usuarios. Para lograr una alta disponibilidad, se recomienda designar un grupo de servidores front-end para esta función.

  - Crear un registro DNS SRV interno para admitir el inicio automático de sesión de clientes para este servidor o grupo de servidores.
    

    > [!NOTE]
    > En los siguientes requisitos de registro, el dominio SIP hace referencia a la parte correspondiente al host de los URI de SIP asignados a los usuarios. Por ejemplo, si los URI de SIP tienen el formato *@contoso.com, contoso.com es el dominio SIP. El dominio SIP suele ser distinto del dominio de Active Directory interno. Una organización también puede admitir varios dominios SIP.



Para habilitar la configuración automática de los clientes, debe crear un registro DNS SRV interno que asigne uno de los registros siguientes al nombre de dominio completo (FQDN) del grupo de servidores front-end o del servidor Standard Edition que distribuya las solicitudes de inicio de sesión de los clientes de Lync:

  - \_sipinternaltls.\_tcp.*\<domain\>*: para las conexiones TLS internas

Solo tiene que crear un único registro SRV para el servidor Standard Edition o el grupo de servidores front-end que distribuirá las solicitudes de inicio de sesión.

En la tabla siguiente se muestran algunos registros de ejemplo que se requieren para la compañía ficticia Contoso, que admite los dominios SIP contoso.com y retail.contoso.com.

### Ejemplo de registros DNS necesarios para el inicio de sesión automático de los clientes con varios dominios SIP

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN del grupo de servidores front-end utilizado para distribuir las solicitudes de inicio de sesión</th>
<th>Dominio SIP</th>
<th>Registro DNS SRV</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>Registro SRV para el dominio _sipinternaltls._tcp.contoso.com sobre el puerto 5061 que se asigna a pool01.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Registro SRV para el dominio _sipinternaltls._tcp.retail.contoso.com sobre el puerto 5061 que se asigna a pool01.contoso.com</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> De forma predeterminada, las consultas de los registros DNS observan estrictamente la coincidencia de los nombres de dominio entre el dominio del nombre de usuario y el registro SRV. Si prefiere que las consultas DNS de los clientes usen la coincidencia de sufijos, puede configurar la directiva de grupo DisableStrictDNSNaming. Para obtener más información, consulte <A href="lync-server-2013-planning-for-clients-and-devices.md">Planeación de clientes y dispositivos en Lync Server 2013</A> en la documentación sobre planeación.



## Ejemplo de los certificados y registros DNS requeridos para el inicio de sesión automático de los clientes

En este ejemplo se utilizan los mismos nombres de ejemplo de la tabla anterior. La organización Contoso admite los dominios SIP de contoso.com y retail.contoso.com, y todos sus usuarios tienen un URI de SIP con uno de los formatos siguientes:

  - *\<user\>*@retail.contoso.com

  - *\<user\>*@contoso.com

