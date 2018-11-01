---
title: "Lync Server 2013: Resumen DNS: Servidor perim. ampliado con equilibr. carga hardware"
TOCTitle: Resumen DNS - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48275887
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen DNS - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Los requisitos de registro DNS para tener acceso de manera remota a Lync Server 2013 son bastante sencillos en comparación con los de los certificados y los puertos. Además, muchos registros son opcionales, en función de cómo configure los clientes de Lync 2013 y de si habilita la federación.

Para más información sobre los requisitos de DNS de Lync 2013, vea [Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Para obtener información detallada sobre la configuración automática de clientes de Lync 2013 si no está configurado el DNS de cerebro dividido, vea "Configuración automática sin DNS de cerebro dividido" en [Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

En la siguiente tabla se incluye un resumen de los registros DNS que se requieren para admitir la figura Topología perimetral consolidada (carga de hardware equilibrada). Tenga en cuenta que ciertos registros DNS solo se requieren para la configuración automática de clientes de Lync. Si piensa usar objetos de directiva de grupo (GPO) para configurar clientes de Lync, los registros asociados no son necesarios.

## IMPORTANTE: requisitos de adaptador de red de Servidor perimetral

Para evitar problemas de redirección, compruebe que haya, como mínimo, dos adaptadores de red en los Servidores perimetrales y que la puerta de enlace predeterminada esté configurada solo en el adaptador de red asociado a la interfaz externa. Por ejemplo, como se muestra en la figura Escenario perimetral consolidado escalado en [Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), la puerta de enlace predeterminada apuntaría al firewall externo.

Puede configurar dos adaptadores de red en cada uno de los Servidores perimetrales como se indica a continuación:

  - **Adaptador de red 1 (Interfaz interna)**
    
    Interfaz interna con 172.25.33.10 asignado.
    
    No hay ninguna puerta de enlace predeterminada.
    
    Asegúrese de que hay una ruta desde la red que contiene la interfaz interna de Servidor perimetral hasta cualquier red que contenga los clientes o servidores de Lync Server que ejecutan Lync Server (por ejemplo, de 172.25.33.0 a 192.168.10.0).

  - **Adaptador de red 2 (Interfaz externa)**
    
    Se asignan tres direcciones IP públicas a este adaptador de red; por ejemplo, 131.107.155.10 para el Servidor perimetral de acceso, 131.107.155.20 para el Servicio perimetral de conferencia web y 131.107.155.30 para el Servicio perimetral A/V.
    

    > [!NOTE]
    > Las direcciones IP que están asignadas a las interfaces de red externa del Servidor perimetral pueden variar en función del equilibrador de carga de hardware que elija. Consulte la documentación del equilibrador de carga de hardware para conocer los requisitos de direcciones IP.<BR>Aunque no lo recomendamos, es posible usar una sola dirección IP para las tres interfaces de servicio perimetral. Si bien esto guarda las direcciones IP, se necesitan números de puerto diferentes para cada servicio. El número de puerto predeterminado es 443/TCP, que garantiza que la mayoría de los firewalls remotos permitirán el tráfico. Cambiar los valores del puerto a (por ejemplo) 5061/TCP para el Servidor perimetral de acceso, 444/TCP para el Servicio perimetral de conferencia web y 443/TCP para el Servicio perimetral A/V puede ocasionarle problemas a los usuarios remotos si se encuentran detrás de un firewall que no permite el tráfico por 5061/TCP y 444/TCP. Además, tres direcciones IP diferentes facilitan la solución de problemas ya que es posible filtrar la dirección IP.

    
    La dirección IP de Servidor perimetral de acceso es la principal, con la puerta de enlace predeterminada establecida en el enrutador integrado (131.107.155).
    
    Las direcciones IP de Servicio perimetral de conferencia web y Servicio perimetral A/V son secundarias.

> [!TIP]  
> La configuración del Servidor perimetral con dos adaptadores de red es una de las dos opciones disponibles. La otra opción es usar un adaptador de red para el lado interno y tres adaptadores de red para el lado externo del Servidor perimetral. La principal ventaja de esta opción es un adaptador de red distinto por servicio de Servidor perimetral, y es necesaria la recopilación de datos potencialmente más concisos al solucionar problemas.



### Registros DNS necesarios para la Topología perimetral consolidada escalada (carga equilibrada con hardware): Topología perimetral consolidada

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/TIPO/Puerto</th>
<th>FQDN/Registro DNS</th>
<th>Dirección IP/FQDN</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>Interfaz externa de Servidor perimetral de acceso (Contoso). Repita según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interfaz externa de Servicio perimetral de conferencia web</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Servicio perimetral A/Vfea-webconfedge-service</p></td>
</tr>
<tr class="even">
<td><p>DNS externo/SRV/443</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaz externa de Servidor perimetral de acceso. Necesaria para la configuración automática de clientes de Lync 2013 y Lync 2010 para que trabajen de manera externa. Repita tantas veces como sea necesario para todos los usuarios de Lync habilitados.</p></td>
</tr>
<tr class="odd">
<td><p>DNS externo</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaz externa de SIP Servidor perimetral de acceso requerida para la recuperación automática de DNS de su federación a otros posibles socios de la federación, y es conocida como &quot;Dominios SIP permitidos&quot; (llamados federación mejorada en versiones anteriores). Repita según sea necesario para todos los dominios SIP con usuarios habilitados por Lync y clientes Microsoft Lync Mobile que usan el Servicios de notificaciones de inserción o el Servicios de notificaciones de inserción de Apple.</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interfaz perimetral interna consolidada</p></td>
</tr>
</tbody>
</table>

