# GitHub Copilot Demos

## Powershell

``` Powershell

$jan=1
$feb=2
$mar=3
$apr=4
$may=5
$jun=6
$jul=7
$aug=8
$sep=9
$oct=10
$nov=11
$dec=12

$month = Get-Date -Format MMMM
$month = $month.ToLower()

# Create a hashtable with months and their corresponding numbers
$months = @{
    "january" = $jan
    "february" = $feb
    "march" = $mar
    "april" = $apr
    "may" = $may
    "june" = $jun
    "july" = $jul
    "august" = $aug
    "september" = $sep
    "october" = $oct
    "november" = $nov
    "december" = $dec
}

# Get the number of the current month
$monthNumber = $months[$month]

# Log into Azure
Login-AzureRmAccount

# Get the current subscription
$subscription = Get-AzureRmSubscription

# Create a resource group named tcsrg in the East Us region
New-AzureRmResourceGroup -Name tcsrg -Location "East US"

# Create a resource group if no group exists
if (Get-AzureRmResourceGroup -Name tcsrg -ErrorAction SilentlyContinue) {
    Write-Host "Resource group tcsrg already exists. Skipping creation."
} else {
    Write-Host "Creating resource group tcsrg"
    New-AzureRmResourceGroup -Name tcsrg -Location "East US"
}

# Import the Pester module
Import-Module Pester

# Describe the test suite
Describe "Azure Resource Group Tests" {
    # Mock the Get-AzureRmResourceGroup cmdlet
    Mock Get-AzureRmResourceGroup {}

    # Mock the New-AzureRmResourceGroup cmdlet
    Mock New-AzureRmResourceGroup {}

    # Test for the Get-AzureRmResourceGroup and New-AzureRmResourceGroup block of code
    It "Creates a new resource group if it doesn't exist" {
        if (Get-AzureRmResourceGroup -Name "tcsrg" -ErrorAction SilentlyContinue) {
            Write-Host "Resource group tcsrg already exists. Skipping creation."
        } else {
            Write-Host "Creating resource group tcsrg"
            New-AzureRmResourceGroup -Name "tcsrg" -Location "East US"
        }
        Assert-MockCalled Get-AzureRmResourceGroup -Exactly -Times 1 -Scope It
        Assert-MockCalled New-AzureRmResourceGroup -Exactly -Times 1 -Scope It
    }
}

```

## C-Sharp

1. Copy files from [here](https://github.com/gh-msft-innersource/CopilotPlayground/tree/main/FollowStandards)
2. Close all files in editor
3. No Hints
   1. Open GetProxy.cs
      1. Add comment "// Handle the case where the response is not HTTP OK"
4. With Hints
   1. Open PetProxy.cs
      1. Show handle code
   2. Open GetProxy.cs
      1. Delete Generated code
      2. Re-enter comment
      3. The style should match code in PetProxy.cs

5. Open TestStoreProxy.cs
   1. Show code for handling negative values (_TestGetOrderNegativeId()_)
6. Open StoreProxy.cs
   1. Add comment: "// Handle negative values" at top

## References

See (https://github.com/gh-msft-innersource/CopilotPlayground/tree/main)
