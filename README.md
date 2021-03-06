# DIGGER [![Build Status](https://travis-ci.org/daniesy/php-digger.svg?branch=master)](https://travis-ci.org/daniesy/php-digger)

A simple way to fetch DNS Resource Records associated with a hostname.

### How to

Using digger is easy as 1, 2, 3.

	<?php
	require 'vendor/autoload.php';

	use Daniesy\Digger;

	$records = (new Digger)->getRecords('ping-pong.dev', 'A');
	foreach($records as $record) {
    	var_dump($record);
	}
	
	if($records->has('127.0.0.1')) {
		echo "The dns record is set";
	}

### Installation

You can install `Digger` with composer by running the following command.

`composer require daniesy/php-digger:dev-master`

### Parameters

- **host**
   The host you want to fetch the DNS records from
- **type**
   The type of DNS Records you want to get. At the moment, only the following records are supported: `A`, `AAAA`, `CAA`, `CNAME`, `MX`, `NS`, `PTR`, `SOA`, `SRV`, `TXT`. I'll add more at a later point.
- **timeout**
   The timeout in seconds after which the call should fail. The default timeout is `5` seconds.