# ts

const a = [1,2,3,4,5] as const
const b = [1,2,3,4,5] as const

type IndexOf<
 T extends [], 
 S extends number[] = []
 > = T["length"] extends S["length"] 
   ? S[number] 
   : IndexOf<T, [S["length"], ...S]>;

a.map((_,index:IndexOf<typeof a>) => {
 const c = b[index]
})
