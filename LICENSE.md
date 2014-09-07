package com.bikash.callremotewebservice;

import net.webservicex.GeoIP;
import net.webservicex.GeoIPService;
import net.webservicex.GeoIPServiceSoap;

public class IpLocationFinder {
	public static void main(String[] args) {
		if(args.length !=1)
		{
			System.out.println("Please enter ip address");
		}
		else {
			String ipaddress=args[0];
			GeoIPService ipService=new GeoIPService();
			GeoIPServiceSoap geoIPServiceSoap=ipService.getGeoIPServiceSoap();
			GeoIP geoIP=geoIPServiceSoap.getGeoIP(ipaddress);
			System.out.println(geoIP.getCountryName());
		}
	}

}
