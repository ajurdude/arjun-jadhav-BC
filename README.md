# Ethereum Accounts

   # Owner Account
        main-01 0x36AA276cFb4fb68A7B50Ad4f73daD4dB7D112021

   # Secondary Account
        Account-04 0x88ca31dbe1D26c0150772899F138aEc1F67b1C48
        Account-05 0x28cFcb06C702bec1D47C2F437e382C49849c48e5
        Account-06 0x01Db9E407312216216fc522d1CA38C842C30Adf0

   # ERC20 Contract
        Token Contract Address- 0x23D02Dd16180cC29FDdBa8130564FB6C469318fa

   # Distribute Token

                    function transferFrom(
                address sender,
                address recipient,
                uint256 amount
            ) public virtual override returns (bool) {
                _transfer(sender, recipient, amount);

                uint256 currentAllowance = _allowances[sender][_msgSender()];
                require(currentAllowance >= amount, "ERC20: transfer amount exceeds allowance");
                unchecked {
                    _approve(sender, _msgSender(), currentAllowance - amount);
                }

                return true;
            }

   # How to Execute TRC Token Distribution Node Application (Docker)

        1.  Put the correct private key in .env line 2

            How to get the correct private key?
            Try to decode documents/encrypted_private_key.txt using Salad Chiper shift 7, https://cryptii.com/

        2.  Modify src/addresses.txt, make sure you put correct ETH accounts that you want to transfer, put line break between each of them


