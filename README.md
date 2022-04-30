[![npm](https://img.shields.io/npm/v/@kronos-integration/interceptor-line-header.svg)](https://www.npmjs.com/package/@kronos-integration/interceptor-line-header)
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
[![minified size](https://badgen.net/bundlephobia/min/@kronos-integration/interceptor-line-header)](https://bundlephobia.com/result?p=@kronos-integration/interceptor-line-header)
[![downloads](http://img.shields.io/npm/dm/@kronos-integration/interceptor-line-header.svg?style=flat-square)](https://npmjs.org/package/@kronos-integration/interceptor-line-header)
[![GitHub Issues](https://img.shields.io/github/issues/interceptor-line-header/interceptor-line-header.svg?style=flat-square)](https://github.com/interceptor-line-header/interceptor-line-header/issues)
[![Build Status](https://img.shields.io/endpoint.svg?url=https%3A%2F%2Factions-badge.atrox.dev%2Finterceptor-line-header%2Finterceptor-line-header%2Fbadge\&style=flat)](https://actions-badge.atrox.dev/interceptor-line-header/interceptor-line-header/goto)
[![Styled with prettier](https://img.shields.io/badge/styled_with-prettier-ff69b4.svg)](https://github.com/prettier/prettier)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)
[![Known Vulnerabilities](https://snyk.io/test/github/interceptor-line-header/interceptor-line-header/badge.svg)](https://snyk.io/test/github/interceptor-line-header/interceptor-line-header)
[![Coverage Status](https://coveralls.io/repos/interceptor-line-header/interceptor-line-header/badge.svg)](https://coveralls.io/github/interceptor-line-header/interceptor-line-header)

# API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### Table of Contents

*   [LineHeaderInterceptor](#lineheaderinterceptor)
    *   [Parameters](#parameters)
*   [constructor](#constructor)
    *   [Parameters](#parameters-1)
*   [\_transform](#\_transform)
    *   [Parameters](#parameters-2)
*   [getRealHeaderCheck](#getrealheadercheck)
    *   [Parameters](#parameters-3)
*   [getCheckInfo](#getcheckinfo)
    *   [Parameters](#parameters-4)
*   [getPreCheck](#getprecheck)
*   [getStrictCheck](#getstrictcheck)
    *   [Parameters](#parameters-5)
*   [getMissingColumnCheck](#getmissingcolumncheck)
    *   [Parameters](#parameters-6)
*   [getMandatoryColumnCheck](#getmandatorycolumncheck)
    *   [Parameters](#parameters-7)
*   [foundColumns](#foundcolumns)
    *   [Parameters](#parameters-8)
*   [getAdditionalColumnCheck](#getadditionalcolumncheck)
    *   [Parameters](#parameters-9)

## LineHeaderInterceptor

**Extends Interceptor**

This interceptor cares about the handling of the messages.
It will add the hops and copies the messages

### Parameters

*   `config`  
*   `endpoint`  

## constructor

### Parameters

*   `checkProperty`  
*   `validate`  

## \_transform

Reads the stream data and split it into lines.

### Parameters

*   `data`  
*   `enc`  
*   `cb`  

## getRealHeaderCheck

Creates a check which will match the future columns names to there real position

### Parameters

*   `expectedHeader`  The expected header
*   `caseSensitive`  Is the header case sensitive
*   `fieldNames`  The fieldNames to use for each field.

Returns **any** fieldMap This maps the fieldNames to the position in the array.

## getCheckInfo

Extracts the boolean value and the severity of a given check name from the checkProperty

### Parameters

*   `checkProperty`  The checkProperty as defined in the schema
*   `fieldName`  The name of the field in the checkProperty

Returns **any** infoObject An object containing the boolean value and the severity

## getPreCheck

The pre check will be performed anyhow. It just checks that the content to check exists.

## getStrictCheck

returns the Strict header check

### Parameters

*   `expectedHeader`  The expected header
*   `caseSensitive`  
*   `severity`  

## getMissingColumnCheck

Creates the missing column check

### Parameters

*   `expectedHeader`  The expected header
*   `caseSensitive`  Is the header case sensitive
*   `severity`  The severity if the check fails

## getMandatoryColumnCheck

Creates the mandatory column check. This is every time case sensitive as we used the associated column names.

### Parameters

*   `mandatoryColumns`  The mandatory columns. BUT these are the associated fieldnames, not the original column names
*   `severity`  The severity if the check fails

## foundColumns

### Parameters

*   `the`  coluns found and matched.

## getAdditionalColumnCheck

Creates the additional column check. Additional columns not allowed

### Parameters

*   `expectedHeader`  The expected header
*   `caseSensitive`  Is the header case sensitive
*   `severity`  The severity if the check fails
